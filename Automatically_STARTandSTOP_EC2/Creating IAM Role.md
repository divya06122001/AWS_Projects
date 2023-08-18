<h1 align= "center">Creating our IAM Role using Custom Trust Policy</h1>
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/IAM+Role.png" alt="Logo" width="800" height="400">
</div>
<br />
<h2 align= "left">Creating IAM policies using the JSON editor</h2>
<ol>
  <li>Sign in to the <strong>AWS Management Console</strong> and open the <strong>IAM console</strong> at https://console.aws.amazon.com/iam/
  <li>Upon accessing the <strong>IAM Dashboard</strong>, you'll be presented with a view like the one shown below:</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/IAM+Dashboard.png" alt="Logo" width="800" height="400">
</div>
<br>
  <li>In the navigation pane on the left, choose <strong>Policies</strong>.</li>
  <li>Choose <strong>Create policy</strong>.</li>
  <li>In the <strong>Policy editor</strong> section, choose the <strong>JSON</strong> option.
  <li>Copy the <strong>IAM Policy</strong> from <a href="IAM_Console_Link">here</a>, and paste it in the open policy editor. For details about the IAM policy language, see <a href="IAM_Console_Link">IAM JSON policy reference</a>.</li>
  <li>Ensure there are <strong>no syntax errors</strong> <em>(unlikely but just in case)</em> and remove any if found, then click on the <strong>Next</strong> tab.</li>
  <li>A window will open named as <strong>Review and create</strong>.</li>
  <li>
    <ul>
      <li>For <strong>Name</strong>, provide a name for your IAM Policy (e.g., “EC2_StartandStop_Policy” or “IAMPolicy_STARTINGandSTOPPING_EC2”).</strong></li>.<em> You’re going use this name when you’ll create an IAM role to associate with your Lambda Function</em>.</li>
  <li>Please verify if all the mentioned services, including EC2, CloudWatch Logs, EventBridge and Lambda, are listed under the 'permissions defined in this policy' tab.</li>
  <li>Adding tags is optional, but you have the flexibility to use them as per your requirements.</li>
  <li>Choose Create policy.</li>
  <li>After completing these steps, you’ll encounter a window identical to the one shown previously in Step 5. The created policy will also be displayed in this window this time.</li>
  <li>In the navigation pane, choose Roles.</li>
  <li>Choose Create role.</li>
  <li>Under Trusted entity type, choose Custom trust policy.</li>
  <li>Under Custom trust policy, select the statement and delete it.</li>
  <li>Now, copy this and paste in as a statement.</li>
  <li>"lambda.amazonaws.com", "scheduler.amazonaws.com": This identifies the services that are allowed to assume the role. The services listed are AWS Lambda (<em>lambda.amazonaws.com</em>) and AWS EventBridge (<em>scheduler.amazonaws.com</em>).</li>
  <li>"sts:AssumeRole": This action allows the specified principal (Lambda and EventBridge services) to assume the role.</li>
  <li>Choose Next button.</li>
  <li>On the Permissions policies page, search the name of your policy in the Filter field and select it. Choose Next.</li>
  <li>In Name, review, and create section under Role details, fill following:</li>
  <ul>
    <li>a. Role name: Enter a name for your IAM role, for example “EC2_StartandStop_Rule” or “IAMRole_STARTINGandSTOPPING_EC2”.</li>
    <li>b. Description: You can write a short and clear description for this role to help you quickly understand its purpose when you look at it again.</li>
  </ul>
  <li>Choose Create role.</li>
</ol>
<p>And there you have it! Your IAM role is now fully prepared for use. Happy coding and automating!</p>
