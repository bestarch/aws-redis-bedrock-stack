-------
# Amazon Bedrock & Redis Enterprise Cloud

💪🏼 Introducing the *preview* integration of [Amazon Bedrock](https://aws.amazon.com/bedrock/) and [Redis Enterprise Cloud](https://redis.com/redis-enterprise-cloud/overview/): a game-changer for building LLM applications. This collaboration offers a robust, scalable, and efficient solution for developers, streamlining the use of LLMs with Redis as a [vector database](https://redis.com/solutions/use-cases/vector-database). Dive into our new reference architecture to harness the full potential of Retrieval-Augmented Generation (RAG) in your LLM agents.

> [Checkout the official Redis announcement Blog.](http://redis.com/blog/amazon-bedrock-integration-with-redis-enterprise/)

![bedrock-redis-ref-arch.jpg](./docs/assets/bedrock-redis-ref-arch.jpg)

🧠 The above reference architecture highlights [Agents for Amazon Bedrock](https://aws.amazon.com/blogs/aws/preview-connect-foundation-models-to-your-company-data-sources-with-agents-for-amazon-bedrock/) and Redis Enterprise Cloud as the knowledge base for RAG as well as the LLM Cache. The Bedrock integration handles the following for customers:
1. Loading raw source documents from Amazon S3
2. Chunking and creating vector embeddings with a chosen LLM
3. Storing and indexing embeddings within Redis Enterprise Cloud as a vector database
4. Performing semantic search to extract relevant context from the vector database during [RAG](https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-foundation-models-customize-rag.html)

⚡ Additionally, Redis should be utilized as an [LLM Cache](https://www.redisvl.com/docs/html/user_guide/llmcache_03.html) to improve throughput of responses while cutting down on costs.

------

# Getting Started

Use the [official Redis Cloud docs](https://docs.redis.com/latest/rc/cloud-integrations/aws-marketplace/aws-bedrock/) to get started, or for a more step-by-step experience, follow the guides below:

## Redis Enterprise Cloud Setup
To setup Redis Enterprise Cloud as your vector database via the AWS Marketplace, please follow the instructions [here](./docs/redis-enterprise-cloud-setup.md).

## AWS Secrets Manager Setup
To add your deployed database credentials to AWS Secrets Manager, please follow along [here](./docs/aws-secret-manager-setup.md).

## Vector Index Creation
To create your Bedrock vector index in Redis, please follow the instructions [here](./docs/vector-index-creation.md).

## End to End Worked Example
COMING SOON

_____


# Community Examples
Go ahead and get a taste of AWS Bedrock by running a few [examples](./examples) yourself. These will continuously update once the integration is live and as community developers add more examples.

# Need help?
Having issues with the integration? [Get in touch with a Redis expert today](https://redis.com/cloud-partners/aws/#redis_expert). Report other issues on the github repo here by opening an issue.
