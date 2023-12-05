<a name="readme-top"></a>
<!-- PROJECT LOGO -->
<div align="right">
  <a href="https://github.com/divya06122001/AWS_Projects">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Title-Image.png" width="900" height="350">
  </a>
</div>

<a name="readme-top"></a>
<h2 align="center">Efficient EC2 Management: Automating the Start and Stop of EC2 Instances with AWS Lambda and Amazon EventBridge</h2>
<div align="center">
  <h3 style="color: #1E90FF; text-decoration: underline;">🪄 Welcome to the enchanting world of AWS wonders! 🪄</h3><strong>This project is like a tech magician's dream, where AWS services, Amazon EventBridge, and AWS Lambda join forces to conjure up some serious automation magic.</strong>
</div>
<br />
<div align="justify">
  
  <strong><span style="color: #ff9900;">⚙️ Imagine EC2 instances gracefully following preset schedules</strong> like a well-choreographed <strong>dance routine!</strong> 💃 With a <strong>wave of digital fairy dust ✨,</strong> we make <strong>starting and stopping of instances like a walk in the cloud park.</strong><br />

  <strong><span style="color: #ff9900;">✨ Resource management levels up, costs take a backseat in our cloud-powered sleigh</strong> 🛷💰, and the result? <i>A show that's all about resource mastery!</i><br />
    
  <strong><span style="color: #ff9900;">🔮 Oh, but there's more to this tech tale!</span></strong> Our <strong>automated instance maestros also double as security guardians</strong> 🛡️, orchestrating a <strong>symphony of operational efficiency.</strong> It's like having a team of <strong>virtual superheroes at your service!</strong> 🦸‍♂️🌟<br />
    
  <strong><span style="color: #ff9900;">✨ So buckle up, fellow adventurers!</span></strong> Cloud computing meets fantasy in this <strong>epic saga.</strong> Whether you're a <strong>code wizard or just curious about the tech realm,</strong> you're in for a <strong>spellbinding treat!</strong><br />
</div>

<p align="center">🌈 <em>"Automation is the fairy dust that turns dreams into reality"</em> 💭🧚‍♂️✨🔮</p>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
     <li><a href="#project-overview-a-spellbinding-journey-of-automation-and-efficiency">Project Overview</a></li>
     <li><a href="#benefits-unleash-the-power-of-cloud-wizardry">Benefits</a></li>
     <li><a href="#amazon-ec2-introduction-and-key-features">Overview of Amazon EC2</a></li>
     <li><a href="#aws-lambda-introduction-and-key-features">Overview of AWS Lambda</a></li>
     <li><a href="#amazon-eventbridge-introduction-and-key-features">Overview of Amazon EventBridge</a></li>
      <li>
      <a href="#getting-started-begin-your-whimsical-cloud-adventure">Getting Started</a>
      <ul>
       <li><a href="#prerequisites-gearing-up-for-the-enchantment">Prerequisites</a></li>
       <li><a href="#architecture-design-the-art-of-cloud-enchantment">Architecture Design</a></li>
       <li><a href="#implementation-steps-conjure-the-magic-of-aws-lambda-and-eventbridge">Implementation Steps</a></li>
      </ul>
    </li>
      <li><a href="#conclusion-the-grand-finale-of-our-whimsical-cloud-adventure">Conclusion</a></li>
  </ol>
</details>

<!-- PROJECT OVERVIEW -->
## Project Overview: A Spellbinding Journey of Automation and Efficiency
<p style="text-align: justify;">

⚙️ This project is all about <strong><span style="color: #ff9900;">combining the powers of EventBridge Events and Lambda functions,</span></strong> making your <strong>EC2 instances dance to a scheduled rhythm.</strong> Think of it as your very own <strong>orchestra conductor, orchestrating start and stop actions like a pro! 🎶🤖</strong><br>
    
🔮 The <strong><span style="color: #ff9900;">Lambda function becomes the genius behind the curtain 🎩,</span></strong> carrying out those <strong>smart start and stop moves on your EC2 instances.</strong> It talks to <strong>AWS APIs with a wink 😉,</strong> ensuring everything happens smoothly and efficiently. It's like having your very own <strong>tech-savvy butler! 🤵🤖</strong><br>
  
🔗 But wait, there's more! <strong><span style="color: #ff9900;">EventBridge Events swoop in like fairy godmothers,</span></strong> adding a dash of <strong>magic to the mix. ✨✨</strong> You get to <strong>set the rules, creating triggers</strong> that make your <strong>Lambda function spring into action.</strong> Whether it's dealing with <strong>spikes 📈, alarms 🔔, or just regular housekeeping,</strong> this <strong>dynamic duo has got your back! 🦸‍♂️🌟</strong><br>
    
🎉 So, go ahead, <strong><span style="color: #ff9900;">set your instances on autopilot</span></strong> with a <strong>sprinkle of whimsy and a dash of technology.<br>
<br>
🌈🔌</strong> <em>Remember, this isn't just automation; it's your very own <strong>tech fairy tale! 📜✨</strong></em>
</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- BENEFITS -->
## Benefits: Unleash the Power of Cloud Wizardry
 <div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Benefits.jpeg" alt="Logo" width="500" height="300">
 </div>

<div style="text-align: justify;">
   🪐 Ready to discover the wizardry behind automating start and stop processes for EC2 instances? <strong>Here's why it's like having your own spellbook of benefits:</strong>
  <ul><br>
    <li>🧙‍♂️ <strong>Cost Savings:</strong> Watch as your AWS costs shrink faster than a disappearing rabbit! With instances powered on only during working hours, <strong>you'll wave goodbye to wasteful spending and say hello to savings</strong>. 🐇💰</li><br>
    <li>🪄 <strong>Resource Efficiency:</strong> Our magic wands... uh, I mean, automation ensures that instances appear precisely when you need them. <strong>No more ghostly underutilization or monstrous overprovisioning!</strong> 🪄✨</li><br>
    <li>🛡️ <strong>Enhanced Security:</strong> Who needs a guardian spell when instances can vanish and reappear? <strong>Automatically stopping instances during off-hours keeps those pesky security threats at bay</strong>. You become <strong>the sorcerer of safety</strong>! 🔐</li><br>  
    <li>🌿 <strong>Environment-Friendly:</strong> By turning off instances during non-working hours, we're <strong>not just saving gold; we're saving the planet!</strong> Join us on the eco-friendly quest for a greener cloud. 🌍🌱</li><br>
    <li>🌀 <strong>Streamlined Operations:</strong> Tired of manual toil? The automated spells mean <strong>instances are always ready for action. No more manual incantations</strong>—just smooth sailing on the automation breeze! 🌬️🌀</li><br>  
    <li>🌎 <strong>Global Team Collaboration: Whether you're in a different time zone or dimension, our automated magic bridges the gaps.</strong> Collaborate effortlessly and conjure teamwork without timezone troubles! 🌐🤝</li>
  </ul>
So, there you have it! 🎩✨ Embrace the marvels of effective EC2 management through automated start and stop schedules. <strong>It's like having your very own magical carpet ride of cost savings, efficiency, security, and collaboration</strong>. <i>Let's weave this spell together for an enchanted AWS adventure!</i>
</div>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Embark on Your Journey: Introduction to Essential Services
<p align="justify">
As we move forward, you'll discover a <b>beginner-friendly introduction</b> to the essential services used in this project, perfect for those <b>new to the topic</b>. However, if you're already well-versed or have hands-on experience with these services, simply <a href="#getting-started">click here</a> to jump right into getting started! 🚀🌟

<!-- OVERVIEW OF AMAZON EC2 -->
## Amazon EC2: Introduction and Key Features

 <div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Amazon+EC2.jpg" alt="Logo" width="350" height="300">
 </div>
 <br />
<p align="justify"><b>Amazon Elastic Compute Cloud (EC2)</b> is a core web service provided by Amazon Web Services (AWS) that offers <b>scalable and resizable compute capacity in the cloud</b>. It enables users to <b>launch and manage virtual servers</b>, known as instances, with ease, providing the foundation for a wide range of applications, from simple websites to complex enterprise solutions.</p>
<h4>Key Features:</h4>
<p align="justify">
<b>-> Scalability and Flexibility:</b>
<br />
EC2 allows users to quickly scale their computing resources up or down based on demand. This elasticity ensures cost-effectiveness and high performance, as users only pay for the resources they actually use.

<b>-> Multiple Instance Types:</b>
<br />
EC2 offers a diverse set of instance types optimized for various workloads, including general-purpose, compute-optimized, memory-optimized, and GPU instances. Users can select the most suitable instance type for their specific application requirements.

<b>In summary</b>, Amazon EC2 <b>empowers businesses and developers</b> to access <b>scalable, flexible, and cost-efficient compute capacity in the cloud</b>. With its seamless integration and versatile features, <b>EC2 facilitates the deployment and management of applications of all sizes and complexities</b>.
</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- OVERVIEW OF AWS LAMBDA -->
## AWS Lambda: Introduction and Key Features

 <div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Lambda.png" alt="Logo" width="400" height="300">
 </div>
 <br />
<p align="justify">AWS Lambda is a <b>serverless compute service</b> provided by Amazon Web Services (AWS). It enables <b>developers to run code without provisioning or managing servers</b>. Lambda <b>automatically scales and manages the infrastructure</b> required to run the code, ensuring high availability and cost-effectiveness. With Lambda, developers can <b>focus on writing code and building applications without worrying about server management</b>.</p>
<h4>Key Features:</h4>
<p align="justify">
<b>-> Serverless Compute:</b>
<br />
AWS Lambda allows developers to execute code in response to events, such as changes to data in an Amazon S3 bucket, updates to a DynamoDB table, or HTTP requests via Amazon API Gateway. The service abstracts the underlying infrastructure, automatically managing resources as needed, and charging only for the compute time used.

<b>-> Event-Driven Architecture:</b>
<br />
Lambda follows an event-driven architecture, where developers can create functions that automatically respond to events from various AWS services. This decoupled and event-driven approach enables seamless integration between different components of an application.

<b>-> Multiple Language Support:</b>
<br />
Lambda supports multiple programming languages, including Node.js, Python, Java, Go, Ruby, and more. This flexibility allows developers to choose their preferred language for building serverless applications.

<b>In summary</b>, AWS Lambda offers a <b>serverless and event-driven computing platform</b>, allowing developers to execute code in response to various events without worrying about server provisioning. Its <b>automatic scaling and cost-effectiveness</b> make it an ideal choice for <b>building applications that require quick and efficient code execution</b>.
</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- OVERVIEW OF AMAZON EVENTBRIDGE -->
## Amazon EventBridge: Introduction and Key Features
 <div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EventBridge.png" width="750" height="300">
 </div>
 <br />
<p align="justify">Amazon EventBridge is a <b>serverless event-bus service</b> offered by AWS. It simplifies event-driven applications by providing a central event bus where various AWS services, integrated third-party SaaS applications, and custom applications can emit and consume events. EventBridge enables <b>decoupling of application components and supports event routing</b> to specific targets, including AWS Lambda functions, Step Functions, SNS topics, and more.
<h4>Key Features:</h4>
<p align="justify">
<b>-> Event Bus and Schema Registry:</b>
<br />
EventBridge allows developers to define and manage event buses, acting as a central event hub. It also provides a schema registry to define event structure and enforce event data consistency across applications.

<b>-> Event Filtering and Routing:</b>
<br />
With EventBridge, developers can create rules that specify how events are filtered and routed to different targets. This feature enables selective handling of events based on custom criteria, reducing processing overhead and increasing application efficiency.

<b>-> Integrated with AWS Services and SaaS Applications:</b>
<br />
EventBridge seamlessly integrates with various AWS services, including AWS SaaS Partner services like Zendesk, Datadog, and PagerDuty. It allows easy event integration between different applications and services, regardless of their location or environment.

<b>In summary</b>, Amazon EventBridge provides a <b>powerful event-driven architecture for building event-driven applications</b>. It's central event bus and schema registry facilitate <b>efficient event routing and data consistency</b>, enabling developers to create <b>scalable and loosely-coupled applications that respond to events from various sources</b>.
</p>
  
<p align="right">(<a href="#readme-top">back to top</a>)</p>

<a name="getting-started"></a>
<!-- GETTING STARTED -->
## Getting Started: Begin Your Whimsical Cloud Adventure
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Getting+Started.jpg" width="600" height="350">
 </div>

**Oh, absolutely!**
Knowledge is power, and I'm glad you appreciated the importance of understanding the services we're about to work with! 🚀 **But, don't worry, I won't bore you with any more details**. *Let's dive straight into the real magic of this project!* 🧙‍♀️ No more delays, no more jibber-jabber - it's time for the fun stuff! 🎉

**Ready your AWS wand 🪄 and unleash automated EC2 mastery!** 💻 Let's conjure instance magic like never before - *no manual fuss, just finger-flicking finesse!* ✨💫

So, grab your coffee, don your wizard hat (*if you've got it*), and let's rock! 🧙‍♀️🎩 *No more dawdling - AWS is about to dance to our tune!* 💃🕺 Time's precious, let's get enchanting! ⏳🔮

<!-- PREREQUISITES -->
## Prerequisites: Gearing Up for the Enchantment
<p align="justify">
Alrighty then! Before we embark on this exciting journey of EC2 management, let's get a few things sorted out first! 

<b>Step 1: AWS Account - The Key to the Cloud!</b>
<br />
An AWS account is your ticket to the magical realm of cloud computing! If you don't have one yet, *go ahead and create an account* - **it's your passport to all the AWS goodness!** 🧙‍♂️

<b>Step 2: Familiarity with AWS Console - Know Your Way Around!</b>
<br />
While I'll make the process as easy as waving a wand, having some familiarity with the AWS Console will make your adventure even smoother! 🧭 *Take a stroll through the console, no rush!* 🚶‍♂️ If things seem unfamiliar, don't sweat it – **this project is your beginner's guide**. Embrace the learning curve and let's dive in together! 🚀🌟.

<b>Step 3: EC2 Instances with Necessary Tags - Our Secret Sauce!</b>
<br />
Ah, here's a crucial one! Make sure you have some EC2 instances already running with ''special tags'' - *the magic words that will let our Lambda function know which instances to start and stop!* ✨🏷️ **These tags are like secret handshakes for our instances**.

But wait, don't fret - I won't leave you hanging! I'll make sure you have the right tags in place before any magic happens! **No accidental mass shutdowns, I promise!** 😄

<b>You can work your magic and check the enchanting world of EC2 tags following the steps outlined in this mystical document [here](https://github.com/divya06122001/AWS_Projects/blob/main/Automatically_STARTandSTOP_EC2/Check%20and%20Tag%20EC2%20Instances.docx).</b>

Now that, **we've got all our prerequisites sorted**, we're ready to rock and roll with EC2 management like never before! 🎉🚀 Let's dive in and hey, if you have any questions, feel free to ask by creating a new issue - **I'm here to make your EC2 management adventure a delightful one!** 🌈🧁

**So, buckle up, and let's begin this fantastic journey into the world of automated EC2 magic!** 🧙‍♀️✨

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ARCHITECTURE DESIGN -->
## Architecture Design: The Art of Cloud Enchantment
 <div align="center">
<img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/cron-job-arch-diagram.png" width="900" height="600">
 </div>
 
<h3 align="center">Illustration of Architecture of Efficient EC2 Management</h3>

<b>Picture it as a perfectly orchestrated dance between AWS Lambda and Amazon EventBridge</b>, where they team up like mischievous elves to manage EC2 instances effortlessly.

<b>Our star player, the Lambda function, is like the master conductor</b>, waving its coding wand to start and stop EC2 instances on command. 🎩🪄 Meanwhile, <b>EventBridge Scheduler plays matchmaker</b>, ensuring the Lambda function knows exactly when to work its magic. 💘

<b>And guess what?</b> We've got schedules that rival the quirkiest calendars out there! From business hours to weekends and even holidays – our EC2 instances know how to take a break or jump into action just in time! 🗓️🎉

<b>Best part?</b> It's like watching a comedy show with all the cost savings and efficiency gains! Say goodbye to manual hassles, and hello to a cloud ballet of automation. 💸🚀

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- IMPLEMENTATION STEPS -->
## Implementation Steps: Conjure the Magic of AWS Lambda and EventBridge
<div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Implementation+Steps.jpg" alt="Logo" width="500" height="400">
</div>

<p align="justify">
To weave this enchanting solution, follow these mystical steps:

<b>Step 1: IAM Enchantments</b> 🔒🧙‍♀️ 
<br />
-> Craft an **enchanted IAM role** with the **perfect permissions** for your Lambda function. Make sure to follow the ancient wizarding wisdom of **"least privilege"** to keep everything secure!

Here is the first step of this enchanting journey: **[Creating IAM Role](https://github.com/divya06122001/AWS_Projects/blob/main/Automatically_STARTandSTOP_EC2/Step%201%20-%20Creating%20IAM%20Role.md)** – the key to unlocking its enchanted powers! 

<b>Step 2: Create the Lambda Magic</b> ✨🧙‍♂️ 
<br />
-> Conjure up a **brand-new Lambda function**. Choose your **preferred spell (Python, Node.js)** or any magic language to weave the code logic that'll control those EC2 instances with a flick of your wand! 🪄🎩

Delve into the enchanting world of the **[Creating Lambda Function](https://github.com/divya06122001/AWS_Projects/blob/main/Automatically_STARTandSTOP_EC2/Step%202%20-%20Creating%20Lambda%20Function.md)** , where the magic of automation unfolds before your very eyes!

<b>Step 3: Summon the EventBridge Schedules</b>🔮🗓️
<br />
-> Prepare your magic scrolls and create EventBridge schedules. Enchant them with the **perfect schedule or event patterns**, and command them to trigger your **Lambda function's mystical powers**!

Behold! Follow the steps mentioned in the document **[here](https://github.com/divya06122001/AWS_Projects/blob/main/Automatically_STARTandSTOP_EC2/Step%203%20-%20Creating%20Amazon%20EventBridge%20Schedules.md)** to craft your EventBridge Schedule and relish the fruits of your labor! ✨ **Always ensure accuracy by peeking into the future and observing trigger dates**. It's like having a crystal ball for your project's success! 🔮📅

<b>Step 5: CloudWatch Charm:</b> 🔍👁️‍🗨️
<br />
-> Use the **magical CloudWatch to cast spells of monitoring and tracking**. Watch closely as it **reveals the secrets of your Lambda's performance** and **keeps an eye on any mischievous gremlins**!

<b>Step 6: Dance of Automation:</b> 🎉💰💫
<br />
-> Watch in wonder as **your EC2 instances dance to the rhythm of automation**! Celebrate the benefits of cost savings, resource efficiency, and all the magic this spell has brought to your cloud journey!

**With these whimsical steps, you've mastered the art of "Automatically Start and Stop EC2 Instances." Now, embrace the magic, and may your cloud adventures be full of enchantment and laughter! 🌈🧚‍♂️🌟**

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONCLUSION -->
## Conclusion: The Grand Finale of our Whimsical Cloud Adventure!

 <div align="center">
 <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Conclusion.jpg" alt="Logo" width="700" height="400">
 </div>

**Congratulations**, fellow cloud enchanters! **You've now unlocked the secrets of Automatically Start and Stop EC2 Instances using AWS Lambda and Amazon EventBridge**. 🪄🚀

As we **bid adieu** to this magical journey, remember that **cloud sorcery is all about creativity and curiosity**. Embrace the playful spirit of experimentation and continue to weave your own unique spells in the enchanted world of AWS! 🌟🧙‍♀️

Now, go forth and conquer the cloud with confidence! May your projects be brimming with efficiency, cost savings, and a sprinkle of whimsy. Keep exploring, keep learning, and let your imagination soar higher than the highest cloud! ☁️🌌✨

With your newfound mastery, the **cloud realm is yours to shape**. So, wave your wands of innovation and build enchanted solutions that leave the world in awe! Remember, the **journey of a cloud sorcerer never truly ends** — it's an eternal dance of learning and enchantment! 🎶🌟🔮

**[Thank you](https://github.com/divya06122001/AWS_Projects/blob/main/Automatically_STARTandSTOP_EC2/A%20Magical%20Journey%20-%20Thank%20You%2C%20Dear%20Reader.md) for joining us on this whimsical adventure. Until we meet again in the realms of cloud magic! 🌈🧚‍♂️💫**

<p align="right">(<a href="#readme-top">back to top</a>)</p>
