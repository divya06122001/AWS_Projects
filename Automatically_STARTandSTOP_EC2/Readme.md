<!-- PROJECT LOGO -->
<div align="center">
  <a href="https://github.com/divya06122001/AWS_Projects">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Title-Image.png?response-content-disposition=inline&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEKL%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCmFwLXNvdXRoLTEiRzBFAiEAqeqEtwzoDBw5MWXis3ckMbk%2FjCIQwoxCHNJ2AEBJomcCIGZdCvVjIqD9nYnewWFhKFDF5%2Bs8CXgHTcRNEGnUVZ4sKugCCDsQABoMOTczOTE4MzI1MjQ2Igwx5OKyQxQMFqkA5LMqxQJ3SBisg7YKVSnOSsvIQFi2XZkHs8hdJLpcFzwtd0IsRyuJic%2FTenypjQhQoZFkr2%2FEQqQUtkAAZpj%2BE84v15fNR47bKs%2FzZ8MBBWJ2q4fziqf9HjoDn9EELDLH6HHHWfI58cPVRfsQtGZ3qSd%2FJusanijzM2ulYAKi0UbTDwosw2JZnuNAdSznpkv15m95jIEnXn382wKiw0UoAcglEZ1IHd29fANpirVESG2NvVIizBjUgTlxVvxO0bVR6bDkAlE8UpIijpVqRcurzr6bgZSJ7Kr5w36xE1y5EUpXvyOq7F20jc80gxFcQiiAPxoLW8V8jZC4O5h7u4oBLJA0sk12hk6Fh0v2EB60vodCD9etP5%2BEn6m9gLq%2BYf5k6uFHFahMJ4YbLmH1IejrbJTlpbekaRfhC6s3taE%2BQB2xM%2BU6U%2BHiilwgMPX4gaYGOrMCiy3w%2BOYEch6jA9hlWyTZ7q32l1alpKXx5P55w2dwqH43oC5iDcCwijKuzahtGxheE8QqfwK1SuhRsB0KIoBNdQhRYl5C0RYGoFUyF800QKyrnjrEtprwzEyKJjL9W3gcOTUBoZhXr2tBYuMQgBi8rzD4ugkkvqLhjDvJGP1P2HBv7xPezox5%2FHTdDZwRFVD%2BW7HozZWNRBZWqHhOPYQr1Ed%2FkJT8kURtr5DeEHxeSqC082m5m6IPWYNdi6J%2FBbnuD2lYGaFyk5f%2BmlsA1EJVtQ%2BAUZMSFPHWnZyJQ8B47UayrfT%2BRI4X4VjpFmi6rzZaB%2BKVVE9QXD0pgI1ebZ9ThN0EJW0GLE%2Fbv2WHgIDYUHJI%2F1jS%2FGujvU%2B1owQ1zbnjgsTzSQcVhPA0B5YXy%2FoxMA2BTQ%3D%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20230726T123143Z&X-Amz-SignedHeaders=host&X-Amz-Expires=300&X-Amz-Credential=ASIA6FQQOJH7AKQPAESP%2F20230726%2Fap-south-1%2Fs3%2Faws4_request&X-Amz-Signature=78512a43047c72fef6ce2c29ff5fc519df72709b00e486ea2f4f3a182711e40f" width="1000" height="350">
  </a>
<a name="readme-top"></a>
<h2 align="center">Efficient EC2 Management: Automating Start and Stop EC2 with AWS Lambda and Amazon EventBridge</h2>

<p align="justify">This project showcases the automation of EC2 instances using AWS services, <b>EventBridge and Lambda</b>.
By utilizing these services, the solution enables the automatic starting and stopping of EC2 instances based on predefined schedules, leading to <b>improved resource management</b> and <b>cost optimization in AWS environments</b>.
By automating instance management, businesses can ensure <b>cost-effective and optimized use of AWS resources</b> while <b>improving security and operational efficiency</b>.
    <br />
    <p align="center">
    <a href="https://github.com/divya06122001/AWS_Projects/tree/main/LambdaEC2StartStopAutomatically"><strong>Explore the docs »</strong></a>
    <br />
    ·  
    <a href="https://github.com/github_username/repo_name">View Demo</a>
    ·
    <a href="https://github.com/github_username/repo_name/issues">Report Bug</a>
    ·
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
     <li><a href="#about-the-project">About The Project</a></li>
     <li><a href="#advantages">Advantages</a></li>
     <li><a href="#amazon-ec2-introduction-and-key-features">Overview of Amazon EC2</a></li>
     <li><a href="#aws-lambda-introduction-and-key-features">Overview of AWS Lambda</a></li>
     <li><a href="#amazon-eventbridge-introduction-and-key-features">Overview of Amazon EventBridge</a></li>
      <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
       <li><a href="#prerequisites">Prerequisites</a></li>
       <li><a href="#architecture-design">Architecture Design</a></li>
       <li><a href="#implementation-steps">Implementation Steps</a></li>
      </ul>
    </li>
      <li><a href="#testing-and-validation">Testing and Validation</a></li>
      <li><a href="#monitoring-and-troubleshooting">Monitoring and Troubleshooting</a></li>
      <li><a href="#best-practices-and-considerations">Best Practices and Considerations</a></li>
      <li><a href="#conclusion">Conclusion</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project
<p align="justify">
 This project is a comprehensive automation solution designed to <b>enhance the management of EC2 instances within an AWS environment</b>. By seamlessly integrating <b>EventBridge Events and Lambda functions</b>, this project enables the effortless implementation of automated start and stop actions for EC2 instances based on predefined schedules.

The underlying <b>Lambda function</b> house the intelligent logic responsible for executing the start and stop actions on EC2 instances. <b>Leveraging AWS APIs</b>, the Lambda functions interact seamlessly with EC2 services, providing a reliable and efficient automation mechanism. Users can customize the function's behavior to incorporate additional checks or perform specific tasks before initiating the start or stop process, further enhancing the automation capabilities.

The integration of <b>EventBridge Events</b> provides a highly flexible and customizable event-driven architecture. Users can configure rules and triggers to define precise conditions under which the <b>Lambda function</b> is invoked, allowing for fine-grained control over the start and stop actions. Whether it's scheduling regular maintenance windows or responding to specific events such as user demand spikes or system alerts, this solution offers the versatility to tailor the EC2 instance lifecycle to specific business requirements.
</p>
 
<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ADVANTAGES -->
## Advantages
 <div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Advantage.png" alt="Logo" width="350" height="300">
 </div>

<p align="justify">
Automating the start and stop processes for EC2 instances brings several benefits:

<b>-> Cost Savings:</b>
<br />
Instances are powered on only when needed thus reducing unnecessary running hours and prevent wasteful spending on idle resources resulting in lower AWS costs.

<b>-> Resource Efficiency:</b>
<br />
Automation ensures instances are available precisely when required, maximizing resource utilization, avoiding underutilization and overprovisioning.

<b>-> Enhanced Security:</b>
<br />
Automatically stopping instances during non-business hours reduces the attack surface, minimizes exposure to potential threats and vulnerabilities and thus improves overall security.

<b>-> Environment-Friendly:</b>
<br />
By powering off EC2 instances when they are not needed, we contribute to energy conservation and a greener cloud infrastructure aligning us with sustainability and environmental initiatives.

<b>-> Streamlined Operations:</b>
<br/>
Automated schedules eliminate the need for manual intervention, streamlining management tasks as the instances are ready for use without requiring manual start-up, improving operational efficiency.

<b>-> Global Team Collaboration:</b>
<br />
For teams working in different time zones or regions, automated start and stop schedules enable seamless collaboration and access to shared resources without manual coordination.

<b>In summary</b>, advantages of effective EC2 management with automated start and stop schedules lie in <b>cost savings, resource efficiency, enhanced security, streamlined operations, and improved global team collaboration</b>. Leveraging these benefits ensures <b>optimal use of AWS resources</b> while aligning with <b>business objectives and environmental responsibility</b>.
</p>

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
## Getting Started
Oh, absolutely!
Knowledge is power, and I'm glad you appreciated the importance of understanding the services we're about to work with! 🚀 But don't worry, I won't bore you with any more details. Let's dive straight into the real magic of this project! 🧙‍♀️ No more delays, no more jibber-jabber - it's time for the fun stuff! 🎉

Get ready to wield your AWS wand 🪄 and unleash the power of automated EC2 management! 💻 Let's make those instances start and stop like they've never done before! No more manual tinkering - we'll do it all with a flick of the finger! ✨💫

So, grab your coffee, put on your wizard hat (if you have one), and let's rock and roll! 🧙‍♀️🎩 I promise we won't waste any more of your precious time. It's time to make AWS dance to our tune! 💃🕺

<!-- PREREQUISITES -->
## Prerequisites
<p align="justify">
Alrighty then! Before we embark on this exciting journey of EC2 management, let's get a few things sorted out first! 🚀

<b>Step 1: AWS Account - The Key to the Cloud!</b>
<br />
An AWS account is your ticket to the magical realm of cloud computing! If you don't have one yet, go ahead and create an account - it's your passport to all the AWS goodness! 🧙‍♂️

<b>Step 2: Familiarity with AWS Console - Know Your Way Around!</b>
<br />
While we'll make the process as easy as waving a wand, having some familiarity with the AWS Console will make your adventure even smoother! 🧭 If you're not already acquainted, take a quick stroll around the console to feel more at home.

<b>Step 3: EC2 Instances with Necessary Tags - Our Secret Sauce!</b>
<br />
Ah, here's a crucial one! Make sure you have some EC2 instances already running with special tags - the magic words that will let our Lambda function know which instances to start and stop! ✨🏷️ These tags are like secret handshakes for our instances.

But wait, don't fret - I won't leave you hanging! I'll make sure you have the right tags in place before any magic happens! No accidental mass shutdowns, I promise! 😄

Now that we've got all our prerequisites sorted, we're ready to rock and roll with EC2 management like never before! 🎉🚀 Let's dive in and make your EC2 instances dance to your commands with grace and precision! 💃🕺

Don't worry, I won't leave you hanging without proper guidance. And hey, if you have any questions, feel free to ask - I'm here to make your EC2 management adventure a delightful one! 🌈🧁

So, buckle up, and let's begin this fantastic journey into the world of automated EC2 magic! 🧙‍♀️✨

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ARCHITECTURE DESIGN -->
## Architecture Design
 <div align="center">
<img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/cron-job-arch-diagram.png" width="900" height="600">
 </div>
<h3 align="center">Illustration of Architecture of Efficient EC2 Management</h3>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- IMPLEMENTATION STEPS -->
## Implementation Steps
 <div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Implementation.png" alt="Logo" width="500" height="300">
 </div>
 
<p align="justify">
To weave this enchanting solution, follow these mystical steps:

<b>-> Empower with IAM Roles and Permissions:</b> Bestow the gift of IAM roles upon your Lambda function and EventBridge rules. Grant them the required permissions, but remember to follow the sacred principle of least privilege. Finally, bind these roles to their respective resources for an unbreakable bond.

To create our IAM role, let the [IAM Policy](https://github.com/divya06122001/AWS_Projects/blob/main/LambdaEC2StartStopAutomatically/IAM_Policy_for_Lambda.json) be summoned! 

<b>-> Summon the Lambda Function:</b> Unleash your powers through the AWS Management Console or the mystical AWS CLI to conjure a Lambda function. Customize the function's runtime, magical code, and triggers. Don't forget to bestow any necessary environment variables for its success.

Here is the example of the [Lambda Function](https://github.com/divya06122001/AWS_Projects/blob/main/LambdaEC2StartStopAutomatically/Lambda%20Function.txt) implemented.

<b>-> Craft the EventBridge Rules:</b> Create spellbinding EventBridge rules using the AWS Management Console or the incantations of the AWS CLI. Define the schedules or event patterns that will activate the Lambda function's enchantment.

The schedule details for the START and STOP rule are provided in the accompanying pictures below:

| START Rule                          | STOP Rule                           |
| ----------------------------------- | ----------------------------------- |
| ![EC2_START_Rule](https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EC2StartRule.png) | ![EC2_STOP_Rule](https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/EC2StopRule.png) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- TESTING AND VALIDATING -->
## Testing and Validation
 
 <div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Testing+and+Validation.png" alt="Logo" width="400" height="300">
 </div>
 <br />
<p align="justify">
In the realm of cloud enchantments, thorough testing holds the key to success! 🔍 We must put our solution through rigorous trials to ensure it performs flawlessly. By simulating various scenarios, we'll verify the start and stop functions based on our carefully crafted schedules. We'll also embark on a quest to validate the magical integration between our mighty Lambda and the watchful EventBridge, ensuring that our spells are triggered precisely when needed. With each successful test, our confidence will soar, and we'll be ready to wield the full power of our automated cloud magic! 

Let's dive into a [series of tests] to observe the enchanting performance of our Lambda function, gracefully starting and stopping EC2 instances based on proper EC2 tags.

Let's validate the harmonious connection between our EventBridge rules and the Lambda function by creating and examining a schedule. Through this [enchanting test], we shall ensure that our cloud wizard responds faithfully to the magical triggers!
</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MONITORING AND TROUBLESHOOTING -->
## Monitoring and Troubleshooting

 <div align="center">
  <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Monitoring+and+Logging.png" alt="Logo" width="300" height="300">
 </div>
 <br />
<p align="justify">In the realm of cloud magic, vigilant monitoring 🔍 and logging are essential to ensure our automated processes run without a hitch!  
 <div align="center">
 <img src="" alt="Logo" width="700" height="400">
 </div>
<b>AWS CloudWatch</b> will be our trusty companion in this endeavor, as we leverage its powerful logs and metrics to keep a watchful eye on our Lambda function's performance. This way, we can swiftly identify any lurking issues and troubleshoot them with our arcane knowledge.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONCLUSION -->
## Conclusion

 <div align="center">
 <img src="https://myprojectrelatedimages.s3.ap-south-1.amazonaws.com/EC2StartandStop/Conclusion.jpg" alt="Logo" width="700" height="400">
 </div>
 
Embracing the art of automation with AWS Lambda and EventBridge empowers us with a versatile and scalable solution for optimizing EC2 instances. By harmonizing our infrastructure with real-time demands and bidding farewell to manual tasks, we unlock remarkable cost savings and elevate our cloud management to new heights of efficiency. 

<i>The magic of automation awaits, and the benefits are nothing short of enchanting! 🧙‍♀️</i>

<p align="right">(<a href="#readme-top">back to top</a>)</p>
