<h1 align= "center">Creating an EventBridge schedule using the EventBridge Scheduler console</h1>
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge+Schedules/AWS+EventBridge+Title.png" alt="AWS EventBridge" width="800" height="500">
</div>

<h2 align= "left">Crafting a new EventBridge schedule</h2>
<ol>
  <li>Sign in to the <strong>AWS Management Console</strong>, then open the <strong>EventBridge Scheduler</strong> section of the EventBridge console from <a href= "https://ap-south-1.console.aws.amazon.com/scheduler/home?region=ap-south-1#schedules">here</a>.</li>
  <li>Switch to your desired <strong>AWS region</strong> by selecting it from the <strong>Region</strong> dropdown menu located in the top-right corner of the console.</li><br>

<strong>For those who are completely new to AWS and just starting out</strong>, on the top-right corner of the console, you'll see the name of the <strong>current region</strong> you're in. Click on it. A dropdown menu will appear, showing a list of available AWS regions. Select the region you want to switch to from the list.

  <li>On the <strong>Schedules</strong> page, scroll down and choose <strong>Create schedule</strong>.</li>
  <li>On the <strong>Specify schedule detail</strong> page, in the <strong>Schedule name and description section</strong> do the following:
    <ul>
      <li>For <strong>Schedule name</strong>, enter a name for your schedule. For example: <strong>EC2StartEventSchedule</strong>.</li>
      <li>For <strong>Description - <em>optional</em></strong>, enter a description for your schedule.<br>For example, <strong>A scheduled start event to trigger a Lambda function for initiating the EC2 instance launch</strong>.</li>
      <li>For <strong>Schedule group</strong>, choose a schedule group from the drop-down options. If you haven't previously made any schedule groups, you can choose the <strong>default</strong> for your schedule. To create a new schedule group, choose the <strong>create your own schedule</strong> link in the console description. You use schedule groups to add tags to groups of schedules.</li>
    </ul>
  </li>
  <li>In the <strong>Schedule pattern</strong> section, do the following:
    <ul>
      <li>For <strong>Occurrence</strong>, choose <strong>Recurring schedule</strong> (This schedule is going to run on and on every week, every month, and every year).</li>
      <li>For <strong>Schedule type</strong>, choose <strong>Cron-based schedule</strong> (This schedule will run at specific time in the morning and evening).</li>
      <li>For <strong>Cron expression</strong>, fill as below:

<div align="left">
<br>
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
</ul>

<strong>Please note</strong> that the <strong><em>question mark (?)</em></strong> represents <strong><em>no specific value</em></strong>, the <strong><em>asterisk (*)</em></strong> represents <strong><em>any value</em></strong> and the <strong><em>hyphen (-)</em></strong> represents <strong><em>a range</em></strong>.

