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

1. Open the **Amazon EC2 console** from [here](https://console.aws.amazon.com/ec2/).
<div align="center">
<img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/EC2+Dashboard.png" alt="Logo" width="800" height="400">
</div>
<br />

2. From the navigation bar, select the **Region** where your EC2 instances are located.
3. In the navigation (left sidebar) pane, expand **Instances** and select **Instances** or you can directly click on **Instances** tab under **Resources** section.
4. Make sure you click on **Instances** tab rather than **Instances(running)** tab as it will only show *running instances* at that very moment.
5. Select the instance from the **Instances** window and choose the **Tags** tab.
6. See below pictures as an **example for both Tagged and Non-Tagged Instances**:
<br>

| EC2 Instances with Tags |
:-------------------------:|
![](https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/Checking+Tags+of+EC2.png)
    
| EC2 Instances without Tags |
:-------------------------:|
![](https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/No+Tags.png)

<h2 align= "left">To add tags to an individual EC2 instance</h2>

Follow the above mentioned steps above to check if your EC2 instances are having "tags" or not. Now to add "tags", follow these steps:

1. Choose **Manage tags** button as you see can see in above image, a new window will open.
2. Choose **Add new tag**.
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/New+Tag.png" alt="Logo" width="800" height="400">
</div>
 
3. Enter the **key and value** for the tag.
4. Choose **Add new tag**, if you want to add any additional tag).
5. Look at this example:
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Check+and+Tag+EC2+Instances/Added+New+Tag.png" alt="Logo" width="800" height="400">
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
