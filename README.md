# Build-Apps-w-Serverless
## Maximize Efficiency with Serverless: Explore direct service integrations using Amazon API Gateway, AWS Step Functions, and Amazon EventBridge. Streamline development tasks by prioritizing configuration over custom code. 
# Launch a CloudFormation stack
The AWS CloudFormation template is used to set up lab resources in the AWS Region that you choose. This step is required because later instructions are based on these resources. The CloudFormation template provisions the following resources:

IAM Role.
Amazon DynamoDB table.
AWS Step Functions State Machine.
Download the CloudFormation template: Download

Store the YAML template file in a folder on your local machine.

Navigate to CloudFormation in the AWS Management Console.

On the CloudFormation console, choose Upload a template file.

Select the template that you just downloaded, and then choose Next.
![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/de62051c-f7ad-4d5b-babe-34838dcc2a82)

Give the stack a name, such as serverless-mindset-stack

For Configure stack options, keep the default values and choose Next.

In Capabilities and transforms, acknowledge all.

![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/4318676d-15c1-440b-9804-348759fbcc3f)

To deploy the template, choose Submit.

After the template is deployed, to review the created resources, navigate to CloudFormation Resources, and then select the CloudFormation stack that you created.

Cloud Formation deployment takes 1–2 minutes to complete.

#Setup AWS Step Functions

#Use Amazon Translate from AWS Step Functions

Let’s change this stub to a task calling Translate service. For it, select the “Start” state in the editor and delete it.
![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/ef2a6a10-ae13-40da-be05-d8247e196974)

In the search tab for actions, type TranslateText and drag the TranslateText action into your workflow.
![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/d8f189c7-b7b9-40c5-b6db-3ac5d0f177b2)

This TranslateText action is a direct SDK integration, which actually makes an SDK call to the Amazon Translate service. To make this SDK call, you need to configure it’s parameters. If you select the action and look at the right panel, you will see under the Configuration tab API Parameters section, which allows you to configure a JSON with the parameters. For our first experiment, let’s hardcode values there and test how the SDK integration works. Use the following JSON as API Parameters:
![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/c5081d12-2719-47d2-8afc-0d19a59dc533)

![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/5339aabe-d239-44d8-83a9-306a0c63b122)
Now let’s test our workflow. On the top panel, click Save button and then click Execute.
![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/fa142926-4731-4fe6-a69a-11ec30e8bc85)

Because you hardcoded the API Parameters, you don’t need to pass any data to the state machine so you can use an empty JSON {} in the start execution window and you can click Start Execution button to launch the instance of the workflow, leaving all other parameters unchanged.

![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/7eaa90a8-abb1-46f9-87d0-521f6448ade2)








![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/4779758e-e66b-4b7e-875e-4268d6754734)
You see the workflow definition in the Workflow Studio.

![image](https://github.com/DJ1775/Build-Apps-w-Serverless/assets/161749076/05090735-e8c7-4734-b48c-32249b903b7d)

