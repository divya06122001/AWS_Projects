<h1 align= "center">Creating an IAM Role using Custom Trust Policy</h1>
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/IAM+Role.png" alt="Architecture of IAM Role" width="800" height="400">
</div>

<h4 align="center">Architecture of "Creation of an IAM Role using Custom trust policy"</h4>

<h2 align= "left">Creating IAM policies using the JSON editor</h2>
<ol>
  <li>Sign in to the <strong>AWS Management Console</strong> and open the <strong>IAM console</strong> at https://console.aws.amazon.com/iam/ .
  <li>Upon accessing the <strong>IAM Dashboard</strong>, you'll be presented with a view like the one shown below:</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/IAM_Dashboard.png" alt="IAM Dashboard" width="800" height="400">
</div>
<br>
  <li>In the navigation pane on the left, choose <strong>Policies</strong>.</li>
<br> 
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/IAM+Policy+Dashboard.png" alt="IAM Policy Dashboard" width="800" height="400">
</div>
<br>
  <li>Choose <strong>Create policy</strong>.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Create+Policy.png" alt="IAM Policy - Create Policy" width="800" height="400">
</div>
<br>
  <li>Choose the <strong>JSON</strong> option.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Choosing+JSON.png" alt="IAM Policy - JSON" width="950" height="400">
</div>
<br>
  <li>Copy the <strong>IAM Policy</strong> from <a href="https://github.com/divya06122001/AWS_Projects/blob/main/Automatically_STARTandSTOP_EC2/IAM_Policy.json">here</a>, and paste it in the open policy editor. For details about the IAM policy language, see <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html">IAM JSON policy reference</a>.</li>
  <li>Once added, it will resemble the image below for your reference.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Specify+Permissions.png" alt="IAM Policy - Specify Permissions" width="800" height="400">
</div>
  <li>Resolve any <strong>security warnings, errors, or general warnings</strong> generated during policy validation <em>(unlikely but just in case)</em>.</li>
  <li>Once you've finished adding permissions to the policy, choose <strong>Next</strong>.</li>
  <li>A window will open named as <strong>Review and create</strong>.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Review+and+Create.png" alt="IAM Policy - Review and create" width="950" height="400">
</div>
<br>  
  <li>On the <strong>Review and create</strong> page, provide a <strong>Policy Name</strong> <em>(e.g., “EC2_StartandStop_Policy” or “IAMPolicy_STARTINGandSTOPPING_EC2”)</em> and a <strong>Description (optional)</strong> for the policy that you are creating.</li>
  <li> Review <strong>Permissions defined in this policy</strong> to see the permissions that are granted by policy.</li>
  <li><strong>Please ensure</strong> that all the specified services, – <strong><em>EC2, CloudWatch Logs, Lambda and EventBridge</em></strong>- are appropriately listed. Verify that they match the image below.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Check+Permissions.png" alt="IAM Policy - Check Permissions" width="800" height="400">
</div>
<br>
  <li><strong>Adding tags is optional</strong>, but you have the flexibility to use them as per your requirements.</li>
  <li>Choose <strong>Create policy</strong> to save your newly crafted policy. Once done, you'll see a green flag 🟢🏳️ indicator displaying the policy name you provided, similar to the example shown below.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Created+Policy.png" alt="IAM Policy - Newly Created IAM Policy" width="900" height="350">
</div>
<br>
  <li>You'll also find your newly created policy listed under <strong>Policy name</strong>, conveniently sorted alphabetically.</li>
</ol>
<br />

<h2 align= "left">Creating IAM roles using a custom trust policy</h2> 

<ol>
  <li>In the navigation pane on left, choose <strong>Roles</strong>.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/IAM+Roles+Dashboard.png" alt="IAM Role Dashboard" width="800" height="400">
</div>
<br>
  <li>Next, click on <strong>Create role</strong>, this will initiate the process of creating a new role.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Create+Role.png" alt="IAM Role - Create role" width="800" height="400">
</div>
<br>
  <li>In <strong>Select trusted entity</strong> window, under <strong>Trusted entity type</strong> section, choose <strong>Custom trust policy</strong>.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Choose+Custom+trust+policy.png" alt="IAM Role - Custom trust policy" width="800" height="400">
</div>
<br>
  <li>In the <strong>Custom trust policy</strong> section, select and delete the existing statement. After that, paste the custom trust policy for the role as provided <a href= "https://github.com/divya06122001/AWS_Projects/blob/main/Automatically_STARTandSTOP_EC2/Custom%20trust%20policy.txt">here</a>.</li>
  <li>Resolve any <em>security warnings, errors, or general warnings</em> generated during policy validation, and then choose <strong>Next</strong>.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Added+Custom+trust+policy+.png" alt="IAM Role - Added Custom trust policy" width="800" height="400">
</div>
<br>  
  <li>On the <strong>Add permissions</strong> page, under <strong>Permissions policies</strong>, select the check box next to the IAM policy you just created or search the name of your policy in the Filter field and select it. For simplicity, leave <strong>Set permissions boundary - optional</strong> as default.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Add+permissions.png" alt="IAM Role - Add permissions" width="800" height="400">
</div>
<br>
  <li>Choose <strong>Next</strong>.</li>
  <li>In <strong>Name, review, and create</strong> window under Role details section, fill following:</li>
  <ul>
    <li><strong>Role name:</strong> Enter a name for your IAM role, for example “EC2_StartandStop_Rule” or “IAMRole_STARTINGandSTOPPING_EC2”.</li>
<strong>IMPORTANT:</strong> Role names need to be different from each other in your AWS account, regardless of whether they are in uppercase or lowercase. Once a role is created, its name cannot be changed.
    <li><strong>Description:</strong> You can write a short and clear description for this role to help you quickly understand its purpose when you look at it again. But, it is totally optional.</li>
  </ul>
  <li>Refer to the image below for visual guidance on the aforementioned steps.</li>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/IAM+Role+-+Review+and+Create.png" alt="IAM Role - Review and Create" width="800" height="400">
</div>
  <li>You can select <strong>Edit</strong> in either the <strong>Step 1: Select trusted entities</strong> or <strong>Step 2: Add permissions</strong>  sections to modify the custom policy and permissions for the role, but remember to make edits only if needed to maintain the role's alignment with your requirements.
  <li>Review the role and then choose <strong>Create role</strong>.</li>
  <li>After completing these steps, you'll once again be greeted by a green flag 🟢🏳️ indicator, displaying the role name you provided – just like you observed when you created the IAM policy. Your newly created policy will be conveniently listed under <strong>Role name</strong>, thoughtfully sorted in alphabetical order. </li>
</ol>
<br>  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/IAM+Role/Created+Role.png" alt="IAM Role - Newly Created IAM Role" width="950" height="350">
</div>
<br />


<p align= "center"><strong><em>🌟🌈 And there you have it! Your IAM role is now fully prepared for action. 🚀 Embrace the power of automation and code confidently, knowing that your role is set up to orchestrate tasks seamlessly. Happy coding and automating! 💻🤖</em></strong></p>

