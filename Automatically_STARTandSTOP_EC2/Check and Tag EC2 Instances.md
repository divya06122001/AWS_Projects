<h1 align= "center">Check and Add "Tags" on individual EC2 Instances</h1>
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/AWS+EC2+Tags.jpeg" alt="Logo" width="700" height="350">
 </div>
 <br />
 
<p align= "center"><strong>Welcome to the guide on checking and tagging your EC2 instances for better management and organization! 👋🔍</strong></p> 

## Why Check and Tag?

EC2 instances are the building blocks of your cloud infrastructure. **By checking and tagging them effectively**, one can gain several benefits:

- **Organization**: Tags help categorize instances by purpose, team, environment, etc.
- **Cost Management**: Properly tagged instances allow for accurate cost allocation.
- **Monitoring**: Tags assist in tracking and managing instances in your monitoring tools.
  
<h2 align= "left">To check tags of an individual EC2 instance</h2>

<ol>
 <p><li>Sign in to the <strong>AWS Management Console</strong> and open the <strong>Amazon EC2 console</strong> from <a href= "https://console.aws.amazon.com/ec2/">here</a>.</li></p>
 <p><li>Upon accessing the <strong>IAM Dashboard</strong>, you'll be presented with a view like the one shown below:</li></p>
  
<div align="center">
<img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/EC2+Dashboard.png" alt="Logo" width="800" height="400">
</div>
<br>

<li>In the <strong><em>top-right corner of the navigation bar</em></strong>, click on the name of the <strong>Region</strong> that is currently shown. Then, pick the <strong>Region</strong> where your EC2 instances are based.</li>

 <p><li>Select <strong>Instances</strong> under <strong>Resources</strong> section. Make sure you click on <strong>Instances</strong> tab rather than <strong>Instances(running)</strong> tab as it will only show <strong><em>running instances</em></strong> at that very moment.</li></p>
   
 <p><li>From the list of instances, find the <strong>specific EC2 instance</strong> you wish to tag and then click on it.</li></p>

 <p><li>In the <strong>Details</strong> section at the bottom, there's a tab labeled <strong>Tags</strong> at the last. Click on it.</li></p>
 
 <p><li>Take a look at the pictures below as examples, <strong>one showing EC2 Instances with Tags</strong> and the <strong>other showing EC2 Instances without Tags</strong>.</li></p>
</ol>

| EC2 Instances with Tags |
:-------------------------:|
![](https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/Checking+Tags+of+EC2.png)
    
| EC2 Instances without Tags |
:-------------------------:|
![](https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/No+Tags.png)

<br>
<br>
<h2 align= "left">To add tags to an individual EC2 instance</h2>

Follow the above mentioned steps above to check if your EC2 instances are having "tags" or not. Now to add "tags", follow these steps:
<ol>
  <p><li>Once you click on the <strong>Tags</strong> tab, you'll find a button called <strong>Manage Tags</strong> on the right side. You can see it in the pictures above.</li></p>
  <p><li>Click on <strong>Manage tags</strong> and a new window will open just like the one shown below:</li></p>

<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/New+Tag.png" alt="Logo" width="900" height="400">
</div>

  <p><li>Click on <strong>Add new tag</strong>.</li></p>
  <p><li>Enter the <strong>key and value</strong> for the tag.</li></p>
  <p><li>Choose <strong>Add new tag</strong>, if you want to add any additional tag.</li></p>
  <p><li>Take a look at this example:</li></p>
  
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/Added+New+Tag.png" alt="Logo" width="900" height="400">
</div>

6. For this project, you must make sure that one of the **Tag: Value** pairs should be **Project: UAT** as it will be easy to understand.
7. You can also use your **own defined tags** but then you have to change the **DEFAULT_TAGS** value when modifying Lambda function (You'll come to understand it once you create a Lambda function). 
8. When you are finished adding tags, click on **Save** button.
9. Now, check again to see the updated tags and it will look something like this:
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/Updated+Tags.png" alt="Logo" width="800" height="400">
</div>   

10. I've repeated the outlined procedure and accomplished the addition of a tag to another EC2 instance. Keeping things organized and efficient is the key!
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/Updated+Tags+of+second+EC2+instance.png" alt="Logo" width="800" height="400">
</div>

<h2>Conclusion</h2>

<p>By effectively <strong>checking and tagging your EC2 instances</strong>, you're enhancing visibility, cost management, and overall organization within your cloud environment. <strong><em>Remember, a well-organized cloud is a happy cloud! ☁️✨</em></strong></p>
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/Happy+Cloud.jpg" alt="Logo" width="450" height="300">
</div>
<br />
<p>To learn more, check out the <a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html">AWS documentation on EC2 tagging</a>.</p>
<br />
<p align= "center"><strong><em>✨ With your EC2 instances neatly adorned with tags and everything perfectly in place, you're now well-prepared to gracefully <a href="#next-step">move on to the next step</a> ✨. Wishing you a productive and rewarding journey through your documentation tasks! 📝</em></strong></p>
