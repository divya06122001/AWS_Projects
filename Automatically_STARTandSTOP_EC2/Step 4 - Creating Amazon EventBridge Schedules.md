<h1 align= "center">Crafting a schedule using the EventBridge Scheduler console</h1>
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Title+Image.png" alt="Title Image" width="800" height="500">
</div>

<h2 align= "left">Creating a new EventBridge schedule</h2>
<ol>

  <p><li>Sign in to the <strong>AWS Management Console</strong> and open the <strong>EventBridge Scheduler</strong> section from <a href= "https://ap-south-1.console.aws.amazon.com/events/home?region=ap-south-1#/">here</a>.</li></p>
  
  <p><li>A dashboard will open which is Amazon EventBridge dashboard shown in picture below:</li></p>

<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/EventBridge+Dashboard.png" alt="AWS EventBridge Dashboard" width="950" height="350">
</div>

  <p><li>Switch to your desired <strong>AWS region</strong> by selecting it from the <strong>Region</strong> dropdown menu located in the top-right corner of the console.</li></p>
  <p><li>On the Dashboard page, click on <strong>EventBridge Schedule</strong> option and then choose <strong>Create schedule</strong>.</li></p>
  <p><li>You will encounter a window that resembles the one shown below.</li></p>

<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Specify+schedule+detail+.png" alt="AWS EventBridge Schedule" width="950" height="350">
</div>

  <p><li>On the <strong>Specify schedule detail</strong> page, in the <strong>Schedule name and description section</strong> do the following:
    <ul> 
      <p><li>For <strong>Schedule name</strong>, enter a name for your schedule. For example: <strong>EC2StartEventSchedule</strong>.</li></p>
      <p><li>For <strong>Description - <em>optional</em></strong>, enter a description for your schedule.<br>For example, <strong>A scheduled start event to trigger the Lambda function for initiating the EC2 instance launch</strong>.</li></p>
      <p><li>For <strong>Schedule group</strong>, choose a schedule group from the drop-down options. <br>
        Certainly, you can choose the <strong>default</strong> option. However, I recommend having a dedicated schedule group. <strong>Why?</strong> Because, <strong><em>Schedule groups allows you to categorize and organize multiple schedules for better management and control for each specific schedule.</em></strong>
        <ol>
          <p><li>To <strong>create a new schedule group</strong>, click on the anchor text <strong>create your own schedule group</strong> written under the schedule group heading.</li></p>
          <p><li>A new window will open shown as below:</li></p>
          <div align="center">
            <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Create+Schedule+Group.png" alt="EventBridge Schedule Group" width="850" height="350">
          </div>
          <p><li>For <strong>Name</strong>, enter a name for your schedule group. For example: <strong>EC2_Schedule_Group</strong>.</li></p>
          <p><li>Click on <strong>Add new tag</strong> if you want to add tags to your schedule group.</li></p>
          <p><li>Now, click on <strong>Create schedule group</strong>.</li></p>
          <p><li>You have successfully created a new schedule group. Now, close this window and go back to the previous one.</li></p>
        </ol>
      </li></p> 
      <p><li>Now, just pick your newly created <strong>(EC2_Schedule_Group)</strong> from the drop-down list of <strong>Schedule group</strong>.</li></p>
    </ul>
  </li></p>
    
  <p><li>In the <strong>Schedule pattern</strong> section, do the following:
      <ul>
        <p><li>For <strong>Occurrence</strong>, choose <strong>Recurring schedule</strong> (This schedule is going to run on and on every week, every month, and every year).</li></p>
        <p><li>For <strong>Schedule type</strong>, choose <strong>Cron-based schedule</strong> (This schedule will run at specific time in the morning and evening).</li></p>
        <p><li>For <strong>Cron expression</strong>, fill as below:</li></p>
              <div align="left">
              <table style="border-collapse: collapse; border: 2px solid #444;">
                <tr>
                  <th>Minutes</th>
                  <th style="border: 1px solid #444; padding: 6px 12px;">Hours</th>
                  <th>Day of Month</th>
                  <th>Month</th>
                  <th style="border: 1px solid #444; padding: 6px 12px;">Day of the Week</th>
                  <th>Year</th>
                </tr>
                <tr align="center">
                  <td>30</td>
                  <td style="border: 1px solid #444;">8</td>
                  <td>?</td>
                  <td>*</td>
                  <td style="border: 1px solid #444;">Mon-Fri</td>
                  <td>*</td>
                </tr>
               </table>
              </div>
        <p><li><strong>Please note</strong> that the <strong><em>question mark (?)</em></strong> represents <strong><em>no specific value</em></strong>, the <strong><em>asterisk (*)</em></strong> represents <strong><em>any value</em></strong> and the <strong><em>hyphen (-)</em></strong> represents <strong><em>a range</em></strong>.</li></p>
      </ul>
  </li></p>

  <p><li>To verify the accuracy of the cron expressions, check the <strong>next 10 trigger dates</strong>.</li></p>

  <p><li>For <strong>Flexible time window</strong>, choose <strong>Off</strong> to turn off the option.</li></p>

  <p><li>In the <strong>Timeframe</strong> section, specify your <strong>Timezone</strong>.</li></p>

  <p><li>It is <em>totally optional</em> to set both the <strong>start date and time</strong> and an <strong>end date and time</strong> for the schedule.
    <ul>
      <p><li><strong>A recurring schedule without a start date will begin as soon as it is created and available.</strong></li></p>
      <p><li><strong>A recurring schedule without an end date will continue to invoke its target indefinitely.</strong></li></p>
    </ul>
  </li></p>

  <div align="center">
    <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Timeframe.png" alt="AWS EventBridge Timeframe" width="900" height="350">
  </div>

  <p><li>Choose <strong>Next</strong>.</li></p>
  <p><li>On the <strong>Select target</strong> page, do the following:
    <ul>
      <p><li>Under <strong>Target API</strong>, select <strong>Templated targets</strong> and choose <strong>AWS Lambda Invoke</strong>.</li></p>
      <p><li>Take a look at the image below to get a clearer understanding of the above mentioned step.</li></p>
      <div align="center">
        <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/EventBridge+Target.png" alt="AWS EventBridge Target" width="850" height="350">
      </div>
      <p><li>In the <strong>Invoke</strong> section, choose the <strong>Lambda function</strong> that we have created previously from the dropdown list.</li></p>
      <p><li>For the <strong>Payload</strong>, provide the below mentioned JSON payload. <strong>Payload is the data sent to EventBridge Scheduler's target during a scheduled event trigger</strong> which in our case, is the <strong>Lambda function</strong>.</li></p>
      
```json
{
  "action": "start"
}    
```
<br>
      <p><li>This JSON message includes a single key-value pair with an <strong>"action"</strong> field set to <strong>"start"</strong>, indicating the desired process to initiate. This tells the <strong>EventBridge Scheduler to tell the Lambda function to start EC2 instances</strong>. It's a way for them to communicate what action needs to be done.</li></p>   
      <p><li>Here, is an image depicting aforementioned steps:</li></p>
      <div align="center">
        <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Invoke+-+Payload.png" alt="AWS EventBridge Invoke and Payload" width="850" height="350">
      </div>
    </ul>
  </li></p>
  
  <p><li>Choose <strong>Next</strong>, then on the <strong>Settings - <em>optional</em></strong> page, do the following:
    <ul>
      <p><li>In the <strong>Schedule state</strong> section, for <strong>Enable schedule</strong>, you can toggle feature on or off using the switch. The <strong><em>EventBridge Scheduler activates your schedule by default</em></strong>, which is the required behaviour.</li></p>
      <p><li>In the <strong>Action after schedule completion</strong> section, choose <strong>NONE</strong> from the dropdown.
          <ul>
            <p><li>If you choose <strong>NONE</strong>, the <strong>EventBridge Scheduler will not take any action</strong> after the schedule completes,  which is the required option.</li></p>
            <p><li>If you choose <strong>DELETE</strong>, the <strong>scheduler will automatically delete the schedule</strong> after it has completed its last invocation and has no future target invocations planned.</li></p>
          </ul>
      </li></p>
    </ul>
  </li></p>

  <div align="center">
    <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Settings+-+Optional.png" alt="AWS EventBridge Settings-Optional 1" width="850" height="350">
  </div>    

  <p><li>In the <strong>Retry policy and dead-letter queue (DLQ)</strong> section, keep all settings as default, but make sure to verify that the values are set to their maximum limits. 
    <ul>
      <p><li>For <strong>Maximum age of event - <em>optional</em></strong>: <strong>24 hours and 0 minutes</strong> so that <em>EventBridge Scheduler must keep an unprocessed event for 24 hours</em>.</li></p>
      <p><li>For <strong>Retry attempts - <em>optional</em></strong>: <strong>185 times</strong> so that <em>EventBridge Scheduler retries the schedule if the target returns an error for 185 times</em>.</li></p>
      <p><li>For <strong>Dead-letter queue (DLQ)</strong>: <strong>None</strong> as we don't want to configure a DLQ now. A Dead-Letter Queue (DLQ) is used to <em>handle messages that fail to process, ensuring proper handling and analysis of problematic messages</em>.</li></p>
    </ul>
  </li></p>

  <div align="center">
    <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Settings+-+Optional+(Part+2).png" alt="AWS EventBridge Settings-Optional 2" width="900" height="350">
  </div>

  <p><li>Leave the settings for <strong>Encryption</strong> as default.</li></p>
  <p><li>Scroll down to <strong>Permissions</strong> section and choose <strong>Use existing role</strong>, since we have already created an IAM role with the necessary permissions.</li></p>
  <p><li>From the drop-down, select the <strong>IAM role</strong> that you've made previously by following the steps mentioned in the document: <a href= "https://github.com/divya06122001/AWS_Projects/blob/main/Automatically_STARTandSTOP_EC2/Step%201%20-%20Creating%20IAM%20Role.md">Step 2 - Creating an IAM Role</a>.</li></p>
  <div align="center">
    <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Settings+-+Optional+(Part+3).png" alt="AWS EventBridge Settings-Optional 3" width="950" height="350">
  </div>

  <p><li>Choose <strong>Next</strong>.</li></p>
  
  <p><li>In the <strong>Review and create schedule</strong> page, review the details of your schedule. In each section, you can choose <strong>Edit</strong> to go back to that step and edit its details.</li></p>
  <p><li>Choose <strong>Create schedule</strong> to finish creating your new schedule.</li></p>
  <p><li>You can view a list of your new and existing schedules on the <strong>Schedules</strong> page. Under the <strong>Status</strong> column, verify that the new schedule is <strong>Enabled</strong>.</li></p>
  <div align="center">
    <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/START+Schedule+Detail.png" alt="AWS EventBridge START Schedule details" width="950" height="400">
  </div>
  <p><li>To verify that your schedule invokes the Amazon Lambda target and starts the EC2 instance, check the status of the EC2 instance around the set trigger time i.e., <strong><em>8:30 AM in the morning</em></strong>.</li></p> 
  <p><li>We have created a <strong>Start Schedule</strong> for our EC2 instances but we need to create a <strong>Stop Schedule</strong> too.</li></p>

  
  <!--------------------------------------------------------------  Steps for creating STOP Schedule begins from here  ---------------------------------------------------------->


  <p><li>To create the new <strong>Stop schedule</strong>, follow the above mentioned steps and modify some steps as mentioned below:
    <ul>
      <p><li>In step 6, when editing the <strong>Schedule name and description</strong> section, follow these instructions:
        <ul>
          <p><li>For <strong>Schedule name</strong>, enter the name for your schedule: <strong>EC2StopEventSchedule</strong>.</li></p>
          <p><li>For <strong>Description - optional</strong>, enter the description for your schedule: <strong>A scheduled stop event to trigger our Lambda function for stopping the running EC2 instance</strong>.</li></p>
          <p><li>For <strong>Schedule group</strong>, choose the one we created: <strong>EC2_Schedule_Group</strong>.</li></p>
        </ul>
      </li></p>

      <p><li>Take a look at the image below for reference. Your schedule should match the example shown.</p></li> 
      <div align="center">
        <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/STOP+Event.png" alt="AWS EventBridge STOP Event" width="850" height="350">
      </div>
      
    </ul>
  </li></p>
    
  <p><li>In step 7, when editing the <strong>Schedule pattern</strong> section, follow these instructions for the <strong>Cron expression</strong>:</li></p>
  <div align="left">
      <table style="border-collapse: collapse; border: 2px solid #444;">
        <tr>
          <th>Minutes</th>
          <th style="border: 1px solid #444; padding: 6px 12px;">Hours</th>
          <th>Day of Month</th>
          <th>Month</th>
          <th style="border: 1px solid #444; padding: 6px 12px;">Day of the Week</th>
          <th>Year</th>
        </tr>
        <tr align="center">
          <td>00</td>
          <td style="border: 1px solid #444;">6</td>
          <td>?</td>
          <td>*</td>
          <td style="border: 1px solid #444;">Mon-Fri</td>
          <td>*</td>
        </tr>
      </table>
  </div>  

  <p><li>In step 13, For the <strong>Payload</strong>, provide the below mentioned JSON payload.</li></p>
         
```json
{
  "action": "stop"
}    
```
<br>

  <p><li>Under the <strong>Status</strong> column, verify that the new schedule is <strong>Enabled</strong>.</li></p>
  <div align="center">
    <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/STOP+Schedule+Detail.png" alt="AWS EventBridge STOP Schedule details" width="900" height="400">
  </div>

  <p><li>To verify that your schedule invokes the Amazon Lambda target and stops the running EC2 instance, check the status of the EC2 instance around the set trigger time i.e., <strong>6:00 PM in the evening</strong>.</li></p>

  <p><li>Now that we've set up schedules for both the <strong>Start Event</strong> and the <strong>Stop Event</strong> for our Lambda function, the next step is to wait for the magic to happen. However, before that, <strong>take a look at the status of both events to ensure they are enabled and functioning correctly</strong>.</li></p>
  <div align="center">
    <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/Schedule+Details.png" alt="AWS EventBridge Schedule details" width="900" height="350">
  </div>
  
  <p><li>In the future, if you find that you no longer need to use the schedule, feel free to <strong><em>disable the rule instead of going through the process of deleting and recreating it</em></strong> in case you need it again accidentally. The great news is that <strong>EventBridge doesn't incur charges for disabled schedules</strong>, providing you with <em>extra flexibility in managing your event triggers</em>.</li></p>
  
</ol>


<!-----------------------------------------------------  Steps for effectively scheduling EC2 instances with various tags begins from here  ----------------------------------------------------------->


<br>
<h2 align="left">Effortlessly Extending EC2 Management to Diverse Instances</h2> 

To extend efficient management to diverse EC2 instances, as you saw in the last part of the Lambda function, you should also create a schedule for them to allow for automatic management. While the steps are nearly identical, let me guide you through the process. Here are the steps to achieve this:
<ol>
  <p><li>On the Dashboard page, click on <strong>EventBridge Schedule</strong> option and then choose <strong>Create schedule</strong>.</li></p>
  <p><li>On the <strong>Specify schedule detail</strong> page, in the <strong>Schedule name and description section</strong> do the following:
    <ul>
      <p><li>For <strong>Schedule name</strong>, enter a name for your schedule: <strong>DiverseTaggedEC2Management</strong>.</li></p>
      <p><li>For <strong>Description - <em>optional</em></strong>, enter description for your schedule: <strong>A schedule for efficiently managing various EC2 instances with distinct tags</strong>.</li></p>
      <p><li>For <strong>Schedule group</strong>, choose the previously created schedule group <strong>(EC2_Schedule_Group)</strong> from the drop-down options.</li></p>
    </ul>
  </li></p>
  
  <p><li>In the <strong>Schedule pattern</strong> section, do the following:
      <ul>
        <p><li>For <strong>Occurrence</strong>, choose <strong>One-time schedule</strong> or <strong>Recurring schedule</strong> based on the nature of the event: <strong>Singular</strong> or <strong>Repetitive</strong> respectively.</li></p>
        <p><li>For <strong>Schedule type</strong>, choose <strong>Cron-based schedule</strong>.</li></p>
        <p><li>For <strong>Cron expression</strong>, fill as below:</li></p>
              <div align="left">
              <table style="border-collapse: collapse; border: 2px solid #444;">
                <tr>
                  <th>Minutes</th>
                  <th style="border: 1px solid #444; padding: 6px 12px;">Hours</th>
                  <th>Day of Month</th>
                  <th>Month</th>
                  <th style="border: 1px solid #444; padding: 6px 12px;">Day of the Week</th>
                  <th>Year</th>
                </tr>
                <tr align="center">
                  <td>00</td>
                  <td style="border: 1px solid #444;">8</td>
                  <td>?</td>
                  <td>*</td>
                  <td style="border: 1px solid #444;">Sat</td>
                  <td>*</td>
                </tr>
               </table>
              </div>
        <p><li>Take a casual look at the <strong>Next 10 trigger dates</strong> to confirm accuracy and avoid any potential errors.</li></p>
        <p><li>For <strong>Flexible time window</strong>, choose <strong>Off</strong> to turn off the option.</li></p>
      </ul>
    </li></p>
  <p><li>Click on <strong>Next</strong>.</li></p>
        
  <p><li>On the <strong>Select target</strong> page, choose the AWS API operation that EventBridge Scheduler invokes:
    <ul>
      <p><li>For <strong>Target API</strong>, choose <strong>Templated targets</strong>.</li></p>
      <p><li>Choose <strong>AWS Lambda Invoke</strong>.</li></p> 
    </ul>
  </li></p>
  
  <p><li>In the <strong>Invoke</strong> section, choose the <strong>Lambda function</strong> from the dropdown list, that we have created previously .</li></p>
  <p><li>For the <strong>Payload</strong>, provide the below mentioned <strong>Payload</strong>.</li></p>

```json
{
  "tags": "tag:Project=Prod",
  "action": "start"
}
```

  <p><li>Click on <strong>Next</strong>.</li></p>\
  <p><li>Keeping everything as default, scroll down to bottom and choose <strong>Use existing role</strong> under <strong>Permissions</strong>.</li></p>
  <p><li>Now, choose the previously made IAM role and then click on <strong>Next</strong>.</li></p>
  <p><li>Review all the things and then click on <strong>Create schedule</strong>.</li></p>
  <p><li>Voila, you're done. See the list of schedules and check the status of your newly created schedule.</li></p>
  
</ol>
<br>
<p align= "center"><strong><em>:partying_face:🎉 Congratulations, you've just woven a web of time with your EventBridge schedules! ⏰✨ Now, your events are all set to dance to their own beats. Remember, you're the DJ of this scheduling party! 🎶💃 Keep rocking those automations and let the events unfold in style! 🌟:metal:🌟 </em></strong></p>

