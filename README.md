# Retrieval Augmented Clinical Encounter Demo

## Overview
This demo uses a Retrieval Augmented Generation (RAG) technique to use previously diagnosed conditions from a sample patient's health record to aid a clinician during a clinical encounter. The concept is not meant to be used in the real world, but aims to highlight the art-of-the-possible with generative AI tools such as Amazon Bedrock in a healthcare environment. It also discusses some of the prompt engineering techniques to achieve consistent, high-quality responses from large language models such as Anthropic's Claude (v2).

### Prerequisites
* It can run either in a local environment or in SageMaker Studio with the **`Data Science 3.0`** kernel on an **`ml.t3.medium`** instance.
* The demo was build and tested using boto3 version 1.33.6. Verify that the environment is running a version of boto3 at least 1.33 or higher.
* Verify that model access to Anthropic's Claude v2 is granted to the account being used, see documentation here: [Amazon Bedrock Model Access](https://docs.aws.amazon.com/bedrock/latest/userguide/model-access.html)
* The user or permission context running the notebook needs to have InvokeModel permissions for the **anthropic.claude-v2** Bedrock model

Sample IAM Policy:
```
{
    "Sid": "BedrockInvokeClaudeV2",
    "Effect": "Allow",
    "Action": "bedrock:InvokeModel",
    "Resource": "arn:aws:bedrock:us-east-1::foundation-model/anthropic.claude-v2"
}
```