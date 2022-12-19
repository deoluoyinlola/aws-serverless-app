# aws-serverless-app

* [Description](#description)
* [Pre-requisites](#pre-requisities)
* [Configure Simple Email service](#Configure-simple-email-service)
* [Add a email lambda function](#Add-a-email-lambda-function)
* [Implement and configure the state machine](#Implement-and-configure-the-state-machine)
* [Implement the API Gateway](#Implement-the-API-Gateway)
* [Implement the static frontend application](#Implement-the-static-frontend-application)
* [Cleanup the account](#Cleanup-the-account)

## Description
 The application will load from an S3 bucket and run in browser, communicating with Lambda and Step functions via an API Gateway Endpoint Using the application you will be able to configure reminders for 'the app' to be sent using email. I have section this project into 6 stages and is pattern after Adrian Cantrill serverless project.
 ![ArchitectureEvolutionAll](Docs/ArchitectureEvolutionAll.png)

## Pre-requisites
- [aws](https://aws.amazon.com/) - cloud platform, offers reliable, scalable, and inexpensive cloud computing services.

## Configure Simple Email service
![ARCHITECTURE-STAGE1](Docs/ARCHITECTURE-STAGE1.png)
- Step 1; Verify SES application sending email address;
The application is going to send reminder messages via SMS and Email. It will use the SES. In production, it could be configured to allow sending from the application email, to any users of the application.

Ensure you are logged into an AWS account, have admin privileges and are in the us-east-1 / N. Virginia Region.
Move to the `SES` console https://console.aws.amazon.com/ses/home?region=us-east-1#.

Click on `Verified Identities` under Configuration Click `Create Identity`. Check the `'Email Address'` checkbox. Ideally you will need a sending email address for the application and a receiving email address for your test customer. But you can use the same email for both.

For my application email, the email the app will send from i'm going to use deolulearn+serverless@gmail.com.

Click `Create Identity`. You will receive an email to this address containing a link to click. Click that link, you should received a `Congratulations!` message. Return to the SES console and `Refresh` your browser, the verification status should now be `verified`
Record this address somewhere save as the `Serverless Sending Address`

- Step 2; Verify SES application customer email address;
If you want to use a different email address for the test customer (recommended), follow the steps below;

Click `Create Identity`. Check the `'Email Address'` checkbox for my application email. The email for my test customer is  deolulearn+customer@gmail.com.
Click `Create Identity`. You will receive an email to this address containing a link to click. Click that link
You should see a `Congratulations!` message. Return to the SES console and refresh your browser, the verification status should now be `verified`. Record this address somewhere save as the `Serverless Customer Address`

At this point we have whitelisted 2 email addresses for use with SES.

the `Serverless Sending Address`.
the `Serverless Customer Address`.
![ses-congrat](Docs/ses-congrat.png)
![ses-verify](Docs/ses-verify.png)

## Add a email lambda function

## Implement and configure the state machine

## Implement the static frontend application

## Cleanup the account