<h1 align= "center">Crafting a schedule using the EventBridge Scheduler console</h1>
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/AWS+EventBridge+Title.png" alt="AWS EventBridge" width="800" height="500">
</div>

<h2 align= "left">Creating a new EventBridge schedule</h2>
<ol>
<li>Sign in to the <strong>AWS Management Console</strong> and open the <strong>EventBridge Scheduler</strong> section from <a href= "https://ap-south-1.console.aws.amazon.com/scheduler/home?region=ap-south-1#schedules">here</a>.</li><br>
  
<li>Switch to your desired <strong>AWS region</strong> by selecting it from the <strong>Region</strong> dropdown menu located in the top-right corner of the console.</li><br>
  
<li><strong>For those who are completely new to AWS and just starting out</strong>, on the top-right corner of the console, you'll see the name of the <strong>current region</strong> you're in. Click on it. A dropdown menu will appear, showing a list of available AWS regions. Select the region you want to switch to from the list.</li><br>

<li>On the <strong>Schedules</strong> page, scroll down and choose <strong>Create schedule</strong>.</li><br>

<li>On the <strong>Specify schedule detail</strong> page, in the <strong>Schedule name and description section</strong> do the following:
      <ul>
        <p><li>For <strong>Schedule name</strong>, enter a name for your schedule. For example: <strong>EC2StartEventSchedule</strong>.</li></p>
        <p><li>For <strong>Description - <em>optional</em></strong>, enter a description for your schedule.<br>For example, <strong>A scheduled start event to trigger a Lambda function for initiating the EC2 instance launch</strong>.</li></p>
        <li>For <strong>Schedule group</strong>, choose a schedule group from the drop-down options. Certainly, you can choose the <strong>default</strong> option if you're new to schedule groups. However, I recommend having a dedicated schedule group for each specific schedule for better organization and management.</li>
        <li>To <strong>create a new schedule group</strong>, click on the anchor text <strong>"create your own schedule group"</strong> written under the schedule group heading. You use schedule groups to add tags to groups of schedules.</li>
        To create a new schedule group, click on the anchor text "Create your own schedule" written under the schedule group heading.
      </ul>
    </li><br>
    
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/EventBridge+Schedule.png" alt="AWS EventBridge Schedule" width="950" height="350">
</div>

<li>In the <strong>Schedule pattern</strong> section, do the following:
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
                  <td style="border: 1px solid #444;">2-6</td>
                  <td>*</td>
                </tr>
               </table>
              </div>
          </li>
        <li><strong>Please note</strong> that the <strong><em>question mark (?)</em></strong> represents <strong><em>no specific value</em></strong>, the <strong><em>asterisk (*)</em></strong> represents <strong><em>any value</em></strong> and the <strong><em>hyphen (-)</em></strong> represents <strong><em>a range</em></strong>.</li>
      </ul>
</li><br>  

<li>To verify the accuracy of the cron expressions, check the <strong>next 10 trigger dates</strong>.</li><br>
<li>For <strong>Flexible time window</strong>, choose <strong>Off</strong> to turn off the option.</li><br>
<li>In the <strong>Timeframe</strong> section, specify your <strong>Timezone</strong>.</li><br>
<li> It is <em>totally optional</em> to set both the <strong>start date and time</strong> and an <strong>end date and time</strong> for the schedule.
  <ul>
    <p><li><strong>A recurring schedule without a start date will begin as soon as it is created and available.</strong></li></p>
    <li><strong>A recurring schedule without an end date will continue to invoke its target indefinitely.</strong></li>
  </ul>
</li><br>
<li>Choose <strong>Next</strong>.</li><br>
<li>On the <strong>Select target - <em>optional</em></strong> page, do the following:
  <ul>
      <p><li>Under <strong>Target API</strong>, select <strong>Templated targets</strong> and choose <strong>AWS Lambda Invoke</strong>.</li></p>
      <p><li>In the <strong>Invoke</strong> section, choose the <strong>Lambda function</strong> that we have created previously from the dropdown list.</li></p>
      <p><li>For the <strong>Payload</strong>, provide the below mentioned JSON payload. <strong>Payload</strong> is the data sent to <strong>EventBridge Scheduler's target</strong> i.e., <strong>our Lambda function</strong>, <em>during a scheduled event trigger</em>.</li></p>
    
      {
        “action”: “start”
      }    

This JSON message includes <em>a single key-value pair with an <strong>"action"</strong> field set to <strong>"start"</strong>, indicating the desired process to initiate</em>. This tells the <strong>EventBridge Scheduler to tell the Lambda function to start EC2 instances</strong>. It's a way for them to communicate what action needs to be done.
  </ul>
</li>

<li>Choose <strong>Next</strong>, then on the <strong>Settings - <em>optional</em></strong> page, do the following:
  <ul>
    <p><li>In the <strong>Schedule state</strong> section, for <strong>Enable schedule</strong>, you can toggle feature on or off using the switch. The <strong><em>EventBridge Scheduler activates your schedule by default</em></strong>, which is the required behaviour.</li></p>
    <p><li>In the <strong>Action after schedule completion</strong> section, choose <strong>NONE</strong> from the dropdown.</p>
          <ul>
           <p><li>If you choose <strong>NONE</strong>, the <strong>EventBridge Scheduler will not take any action</strong> after the schedule completes.</li></p>
           <p><li>If you choose <strong>DELETE</strong>, the <strong>scheduler will automatically delete the schedule</strong> after it has completed its last invocation and has no future target invocations planned.</li></p>
          </ul>
    </li>
    <li>In the <strong>Retry policy and dead-letter queue (DLQ)</strong> section, keep all settings as default, but make sure to verify that the values are set to their maximum limits. 
      <ul>
        <p><li>For <strong>Maximum age of event - <em>optional</em></strong>: <strong>24 hours and 0 minutes</strong> so that <em>EventBridge Scheduler must keep an unprocessed event for 24 hours</em>.</li></p>
        <p><li>For <strong>Retry attempts - <em>optional</em></strong>: <strong>185 times</strong> so that <em>EventBridge Scheduler retries the schedule if the target returns an error for 185 times</em>.</li></p>
        <p><li>For <strong>Dead-letter queue (DLQ)</strong>: <strong>None</strong> as we don't want to configure a DLQ now. A Dead-Letter Queue (DLQ) is used to <em>handle messages that fail to process, ensuring proper handling and analysis of problematic messages</em>.</li></p>
        <p><li>For <strong>Encryption</strong>: Leave it unbothered.</li></p>
        <p><li>Scroll down to <strong>Permissions</strong> section and choose <strong>Use existing role</strong>, since we have already created an IAM role with the necessary permissions.</li></p>
        <p><li>From the drop-down, select the <em><strong>IAM role</strong></em> that we've made previously.</li></p>
      </ul>
    </li>
  </ul>
</li>
<li>Choose <strong>Next</strong>.</li><br>
<li>In the <strong>Review and create schedule</strong> page, review the details of your schedule. In each section, you can choose <strong>Edit</strong> to go back to that step and edit its details.</li><br>
<li>Choose <strong>Create schedule</strong> to finish creating your new schedule.</li><br>
<li>You can view a list of your new and existing schedules on the <strong>Schedules</strong> page. Under the <strong>Status</strong> column, verify that the new schedule is <strong>Enabled</strong>.</li><br>
<li>To verify that your schedule invokes the Amazon Lambda target and starts the EC2 instance, check the status of the EC2 instance around the set trigger time i.e., 8:30 AM in the morning.</li><br> 
<li>You can also check <strong>CloudWatch logs</strong> for a more detailed version.</li><br>
<li>Absolutely, feel free to <strong><em>disable a rule rather than going through the process of deleting and recreating it</em></strong>. The good news is that <strong><em>EventBridge doesn't charge for disabled schedules</em></strong>, giving you added flexibility in managing your event triggers.</li>
</ol>
<br />

<p align= "center"><strong><em>:partying_face:🎉 Congratulations, you've just woven a web of time with your EventBridge schedules! ⏰✨ Now, your events are all set to dance to their own beats. Remember, you're the DJ of this scheduling party! 🎶💃 Keep rocking those automations and let the events unfold in style! 🌟:metal:🌟 </em></strong></p>

