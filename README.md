# CloudFormation Macros

## What are Macros?

Macros are functios that can be defined to perform custom actions in CloudFormation that are otherwise not supported natively.

For further information - [AWS CloudFormation Macros](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-macros.html)

Some Examples can be found here - [AWS CloudFormation Macros Examples](https://github.com/awslabs/aws-cloudformation-templates/tree/master/aws/services/CloudFormation/MacrosExamples/)

## Macro to Generate Template URL 

This Macro generates the `TemplateURL` property for a resource of type - `AWS::CloudFormation::Stack` using two additional properties `Bucket` and `Key`

## Use-Case
Since there is a formatting restriction on the `TemplateURL` property, often users find it tedios to mention the URL. This macro would be more convenient and time-saving.

## To test

* Create a stack using the template - `create-macro.yaml`
    - This template would create the Macro and provide the required function to it.
    - In the function, we would check if the Template Url property is present. If not, we would fetch the values for bucket and key properties, create a Url out of it and then, add it to the `TemplateUrl` property 

* For testing purposes, creating a change set with the template - `test-macro.yaml` 
    - Please upload the child stack - `child_stack.yaml` in a test bucket.
