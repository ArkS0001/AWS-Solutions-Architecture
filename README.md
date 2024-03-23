AWS APAC Solutions Architecture virtual experience program on Forage - March
2024

 * Designed and simple and scalable hosting architecture based on Elastic
   Beanstalk for a client experiencing significant growth and slow response
   times.
 * Described my proposed architecture in plain language ensuring my client
   understood how it works and how costs will be calculated for it.
   
![Architecture Diagram](https://github.com/ArkS0001/AWS-Solutions-Architecture/assets/113760964/a8c24b3d-88d7-4d8e-a227-587193de0631)

# You receive a client email request

In this task, imagine you are a solutions architect at AWS. A customer has contacted you because they are having some problems with the way their web application is currently hosted.

Here's what the client has to say: 

To: aws@aws.com
From: Lilly.sawyer@fastier.com
Subject: AWS services for Web Application Hosting

Hi,

My name is Lilly Sawyer and I am the co-founder and CTO of Fastier, the online tool that makes organizing things fast.

You may have seen that we have been in the news recently and have been experiencing some big growth as a result. Unfortunately, this means we’ve been having some difficulties with our website. The response times can be slow during peak periods and sometimes we even have server crashes when it runs out of memory. We also experience some downtime during deployments and don’t have a disaster recovery plan. Based on our current trajectory, we predict we’re going to see consistent linear growth for a while.

Our application is a SPA React Application backed by Python and Flask, with PostgreSQL as a database. It all runs off a single AWS EC2 instance currently (t3.medium, 4GB of RAM).

Can you design an architecture for us that will alleviate the problems we’re experiencing? We are not on a strict budget right now, but at the same time, it’s not unlimited.

Kind regards,
Lilly


Your task is to draft an email reply to Lilly Sawyer

Draft your email to Lilly

# Okay let's get started on the email to Lilly. In the email, you will need to show an architecture diagram and explain: 

    what each part of the architecture is,
    why it was chosen, and
    how the costs are calculated and how they may vary month-to-month - remember you don’t need to give concrete numbers, just an overview!


Your team has come together and decided on the architecture approach. Outlined below is all the information you need to draft your email - you can also refer back to Step 2 to learn about AWS services. 

Read the information and write your response in the text box below. Your response should be approx. 600-700 words. 

We'll show you an example answer on the next step, but we encourage you to give it a go first! 


First - Your team considers the brief:

When deciding on the right AWS solution, your team considers these points:

    The company is a startup. We are lucky because we can provide more of a greenfield approach, and they are more likely to be able to make changes to their application stack. Compared to an enterprise, where change can take a long time, and they may end up only being able to migrate part of their system at a time.
    Again, being a startup, it is probably easy to migrate their data into AWS.
    They have a single server and already experience downtime, so they are probably OK with some downtime during migration and setup.
    Being a mixed API and web app they will need to host some static content as well.


Second - You decide on the solution: 

In this case, we will recommend a solution based on Elastic Beanstalk based on these requirements:

    The customer has a Python application that Elastic Beanstalk has support for.
    The customer will need to scale, and this is one of the fundamental features of Elastic Beanstalk.
    They want to remove downtime when deploying and Elastic Beanstalk’s Blue/Green deployment can assist with this.

The AWS Elastic Beanstalk documentation provides some more information if you want to learn about it! 


Third - Specify the services: 

The services we will use are listed below: 

    Route 53
    Elastic Load Balancing
    Elastic Beanstalk with Autoscaling EC2 Group
    RDS
    S3
    CodePipeline

An additional availability zone for redundancy is proposed but is not necessary.


Fourth - Evaluate!

Importantly, the team recognizes that Elastic Beanstalk is not the only product that we could recommend for this customer! AWS is an open platform and encourages creativity when building solutions. We need to be aware of the pros and cons of each solution and how they will best fit each customer.

Other options like Lambda or Fargate can be more complex to set up. Lightsail and EC2 can be easy but they don’t provide that automatic scaling; the customer can end up paying more because they are running virtual machines that are often not at capacity. However, each of these services also has its own advantages, and depending on the application that’s being built we can provide different recommendations and discuss the options more in-depth with the customer before coming up with the final design.
