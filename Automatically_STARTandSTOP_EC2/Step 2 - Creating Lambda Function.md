<h1 align= "center">Creating Lambda Function</h1>
<div align="center">
  <img src="" alt="Architecture of Lambda Function" width="800" height="400">
</div>

<h4 align="center">Architecture of "Lambda function triggering AWS EC2 instance"</h4>

<h2 align= "left">Creating Lambda Function</h2>
<ol>
<p><li>Sign in to the <strong>AWS Management Console</strong> and open the Lambda console from <a href= "https://console.aws.amazon.com/lambda">here</a>.</li></p>
<p><li>Upon accessing the <strong>IAM Dashboard</strong>, you'll be presented with a view like the one shown below:</li></p>

<div align="center">
  <img src="" alt="Lambda Dashboard" width="800" height="400">
</div>
<br>
<p><li>Click on the <strong>current Region</strong> in the top-right corner, and select/switch to your desired <strong>AWS region</strong> from the dropdown menu.</li></p>
<p><li>Switch to your desired <strong>AWS region</strong> by selecting it from the <strong>current Region</strong> dropdown menu located in the top-right corner of the console.</li></p>
<p><li>Click on <strong>Create function</strong> to begin creating Lambda function.</li></p>
<p><li>Ensure <strong>Author from Scratch</strong> option is selected; if not, select it.</li></p>
<p><li>Now, configure the following settings:
  <ul>
    <p><li><strong>Function name:</strong> Enter a name for the function. For example: <strong>LambdaEC2_STARTandSTOP_Function</strong>.</li></p>
    <p><li><strong>Runtime:</strong> Choose <strong>Python 3.11</strong> or the latest version you find.</li></p>
    <p><li><strong>Architecture:</strong> Choose x86_64.</li></p>
  </ul>
</li></p>

<p><li>Under <strong>Permissions</strong>, expand <strong>Change default execution role</strong> and then choose <strong>Use an existing role</strong> as we have already create one before.</li></p> 
<p><li>The picture below offers a clear overview of the Step 7 and Step 8.</li></p>
<p><li>From the drop-down under <strong>Existing role</strong>, choose the <strong>IAM role</strong> you made beforehand.</li></p>
<p><li>Leave the other settings as default and proceed with the setup. Click on <strong>Create function</strong> to finalize the creation of your Lambda function.</li></p> 

<p><li>Upon clicking Create function button, the <strong>Function overview</strong> dashboard will open, displaying a visual representation of your Lambda function.</li></p>
<p><li>Scroll down, under <strong>Function overview</strong>, choose <strong>Code tab</strong>.</li></p>
<p><li>Under <strong>Code source</strong>, delete the pre-written code and replace it with the following code:</li></p>

```py
import os
import boto3
import logging

DEFAULT_TAGS = os.environ.get("DEFAULT_TAGS")
print("DEFAULT_TAGS", DEFAULT_TAGS)

logger = logging.getLogger()
level = logging.getLevelName(os.environ.get("LOG_LEVEL", "INFO"))
print("Logging level -- ", level)
logger.setLevel(level)

ec2_resource = boto3.resource('ec2')
ec2_client = boto3.client('ec2')
    
def lambda_handler(event, context):
    """
        Function that start and stop ec2 instances schedule and with specific tags<br/>
        :param event: Input event, that should contain action and tags parameters, where tags is a list of comma separates key/value tags.<br/>
        :param context: Lambda context.<br/>
        :return: nothing
    """
    logger.debug(event)

    print("event -- ", event)

    tags = get_tags(event['tags'] if 'tags' in event else DEFAULT_TAGS)
    print("tags -- ", tags)
    instances = get_instances_by_tags(tags)

    if not instances:
        logger.warning('No instances available with this tags')
    else:
        if event['action'] == 'start':
            ec2_client.start_instances(InstanceIds=instances)
            logger.info('Starting instances.')
        elif event['action'] == 'stop':
            ec2_client.stop_instances(InstanceIds=instances)
            logger.info('Stopping instances.')
        else:
            logger.warning('No instances availables with this tags')


def get_tags(tags):
    """
        Method that split comma separated tags and return a formed tags filter<br/>
        :param tags: Comma separated string with the tags values.<br/>
        :return: tags structure
    """
    final_tags = []
    split_tags = tags.split(",")
    for tag in split_tags:
        values = tag.split('=')
        final_tags.append({
            'Name': values[0],
            'Values': [values[1]]
        })
    return final_tags


def get_instances_by_tags(tags):
    """
        Method that filter all ec2 instances and return only the instances with specific tags<br/>
        :param tags: Filter structure with tag values.<br/>
        :return: list of ec2 instances
    """
    response = ec2_resource.instances.filter(Filters=tags)
    print("Response -- ", response)
    for instance in response:
        print("Instance -- ", instance)
    intance_ids = [instance.id for instance in response]
    print("intance_ids -- ", intance_ids)

    return intance_ids
```

<p><li>Choose <strong>Deploy</strong>.</li></p> 

<p><li>Even though the Lambda function has been deployed, it will not function properly since the necessary <strong>environment variables</strong> in the deployed code, such as <strong>DEFAULT_TAGS</strong> and <strong>LOG_LEVEL</strong>, have not been set.</li></p>

<p><li>To set environment varaibles, click on <strong>Configuration</strong> tab, <strong><em>the third one next to Code tab</em></strong>. Choose <strong>Environment variables</strong> from the left pane and then click on <strong>Edit</strong>.</li></p>

<p><li>A new window, similar to the one depicted below, will open. In this window, select <strong>Add environment variables</strong> and input the necessary environment variables along with their respective values as indicated below:</li></p>

<p><li>You have the flexibility to modify the value of <strong>DEFAULT_TAGS</strong> to match your specific <strong><em>Key:Value pair</em></strong> requirements for your <strong>EC2 instance/instances</strong>. Simply update the <strong>tag</strong> with your <strong>specified Key:Value pair</strong> as shown in picture below:</li></p>
  
<p><li>Click on the <strong>Save</strong> button to save the changes.</li></p>
<p><li>Navigate to the <strong>General configuration</strong> section from the left pane and click on the <strong>Edit</strong>.</li></p>

<p><li>Scroll down the page and set the <strong>Timeout</strong> value to <strong>10 seconds</strong>, which is typically sufficient for this operation, ensuring a timely response.</li></p>
<p><li>Without making any further modifications, simply click on the <strong>Save</strong>.</li></p>
<p><li><strong>You're all set! <em>Your Lambda function has been configured</em></strong> and is now awaiting invocation from the <strong><em>EventBridge event schedule</em></strong>.</li></p>
</ol>
<br>
<p align= "center"><strong>However, how can we be sure it will work flawlessly? Is our Lambda function error-proof? Let's find out by creating a test event to verify if the Lambda function will perform as expected based on our configuration.</strong></p>

<!--------------------------------------- Steps for Lambda Test Creation begins from here --------------------------------------------->

<br>
<h2 align="left">Invoking functions with test events</h2> 
<ol>
<p><li>To configure a test event, select the <strong>Test</strong> tab located right next to the <strong>Code</strong> tab</li></p>
<p><li>Configure the <strong>Test event action</strong> to the default option, which is <strong>Create new event</strong>.</li></p>
<p><li>For <strong>Event name</strong>, enter <strong>EC2-Start-Test</strong> or whatever you like.</li></p>
<p><li>Leave all the settings be default and scroll down to <strong>Event JSON</strong>. Choose <strong>Format JSON</strong> and provide the below mentioned JSON payload.</li></p>

 ```json
  {
    "action": "start"
  }
 ```

<p><li>This <strong>JSON payload <em>instructs</em> the Lambda function to start AWS EC2 instance/instances</strong>, indicating the desired action for EC2 management.</li></p>
<p><li>You have the option to save the test configuration, although it's primarily for checking the function's functionality. If you prefer to save it, click the <strong>Save</strong> button and then proceed by selecting the <strong>Test</strong> button. If you'd rather not save it, you can simply begin by selecting <strong>Test</strong>.</li></p>
<p><li>You'll receive an execution result located just below the <strong>Test</strong> tab, under the header <strong>Executing function: succeeded</strong>.</li></p>

<p><li>In the image provided, you can clearly see how the test event's log output vividly illustrates the process.
  <ul>
    <p><li>The <strong><em>5th and 6th lines</em></strong> provide details about the <strong><em>tags we set and the test event we created</em></strong>. Meanwhile, the <strong><em>5th and 6th lines show the IDs of the EC2 instances that matched the tags we specified, and these instances were successfully stopped as the function ran</em></strong>.
    <p><li>This line seems to define default tags for the execution context.</li></p>
  </ul>
</li></p>

<p><li>Navigate to the EC2 console and verify whether the tagged EC2 instances have successfully started running.</li></p>

<p><li>To configure a stop test event, do the same steps from 2-5.</li></p>
<p><li>Just change the Event name in Step 3 to EC2-Stop-Test and change the Event JSON to {“action”: “stop”}.</li></p>
<p><li>Once more, access the EC2 console to verify the tagged EC2 instances have been stopped successfully.</li></p>

“Fantastic job, fine-tuning your Lambda function! 

With this complete, you're all set for the next exciting step. Keep up the great momentum as you continue your journey into the world of AWS.”

But wait!! There is a little surprise for you ahead.

Effortlessly Extending EC2 Management to Diverse Instances

<p><li>If you intend to start/stop different EC2 instances, tagged with distinct criteria (If your EC2 instances lack tags, take the initiative to tag them now), you can achieve this by specifying the unique tags associated in Format JSON as “tags”: “tag: key=value”, without any spaces.</li></p>

<p><li>Replace the key and value by your EC2 instance Key-Value pair.</li></p>

For example:
<p><li>In my case, I had another EC2 instance named as Prodsrv _1 with the tags: 
Project =  Prod (Key-Value pair)
So, I have mentioned it as you can see in the above picture.</li></p>
<p><li>Now, go back to EC2 management console and check the currently mentioned tagged EC2 instance/instances have been stopped.</li></p>


“With your newfound knowledge and the power of tailored tagging, you're now equipped to expertly manage a diverse array of EC2 instances.</li></p>”
