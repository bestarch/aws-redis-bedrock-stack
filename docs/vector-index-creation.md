-------

# Vector Index Creation

## Objective
Post the AWS Bedrock launch, a vector index in Redis is essential to house your vectorized data.

> Prerequisite: Ensure that your Redis Enterprise Cloud database is active with TLS enabled and certificate files (redis_ca.pem, redis_user_crt.pem, and redis_secret_crt.pem) downloaded.

## Setup Procedure
We'll utilize the [RedisInsight](https://redis.com/redis-enterprise/redis-insight/#insight-form) GUI for this task. Follow these steps:

### 1. Install RedisInsight
Download [RedisInsight](https://redis.com/redis-enterprise/redis-insight/#insight-form).

Install and launch the application to see the "Welcome" screen.

![RedisInsight Welcome Screen](#TODO - redis insight starting image)

### 2. Connect to Your Database
Click ADD REDIS DATABASE.

![RedisInsight Add DB Screen](#TODO - redis insight add db screen)

In the Redis Cloud console, locate your deployed database. Click Connect and copy the provided URL.

![Redis Cloud Console](#TODO - redis cloud console copy URL)

Paste this URL into RedisInsight. It should auto-fill the necessary fields.

![URL Paste](#TODO - copy/pasting the url to RI)

Enable TLS authentication and paste the contents of the three aforementioned certificate files.

![Add TLS Certificates](#TODO - add tls certs)

Click "Test Connection" to verify a secure link.

![Test Connection](#TODO - test connection)

### 3. Initiate Vector Index Creation
Navigate to "Workbench" on the sidebar and explore the user guides, focusing on "Vector Similarity Search".

![Navigating to Workbench](#TODO - navigating to workbench)

Choose to create a FLAT index.

>Note: Redis supports two index kinds: FLAT and HNSW. FLAT is apt for smaller datasets needing precision, while HNSW suits larger datasets prioritizing speed over some accuracy. Detailed HNSW parameters are explained here.

![Command Editor](#TODO - open editor for commands)

Adjust the pre-set index creation script. Here's a recommendation:

- Index name: bedrock-idx
- Key prefix: bedrock-doc (This ensures multi-tenancy in your Redis database)
- Vector field: vector with 1532 dimensions, using the COSINE metric (dimensions determined by the chosen LLM)
- Execute the script using the green arrow.

![Run Script](#TODO - show running the index creation script)

**Upon seeing "OK", you're all set to [integrate your database and index with Bedrock](aws-bedrock-configuration.md)!**