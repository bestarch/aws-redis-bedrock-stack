------

# AWS Secret Manager

## Setting up AWS Secrets for Redis Endpoint configurations

It's typically not recommended to hardcode Redis endpoint details such as server host name, username, password etc. The solution is to leverage AWS Secrets manager. Following procedure outlines setting up Redis endpoint configurations as AWS Secrets.

You will need:

```
Redis Enterprise Cloud Database Hostname
Redis Enterprise Cloud Database Port Number
Redis Enterprise Cloud Database Password
Redis Enterprise Cloud Database Server & Client certs for TLS
```
Start from AWS web console and search for `Secret` in the search box. Select `Secrets Manager` service.

![bedrock-secrets-config-1](./assets/bedrock-secrets-config-1.png)

Click on `Store a new secret`.

![bedrock-secrets-config-2](./assets/bedrock-secrets-config-2.png)

Choose `Other type of secret` (Annotation 1) and select `Key/Value` (Annotation 2) and enter values for `username` and `password` (Annotation 3) for youre Redis database endpoint. You add new key/pair values using `+ AddRow` button (Annotation 4)

![bedrock-secrets-config-3](./assets/bedrock-secrets-config-3.png)

For the key `serverCertificate`, enter the contents of the server certificate (ex: `redis_ca.pem` file contents), as shown.

![bedrock-secrets-config-4](./assets/bedrock-secrets-config-4.png)

Similarly for `clientCertificate`, enter the contents of the client certificate (ex: `redis_user.crt`), as shown.

![bedrock-secrets-config-5](./assets/bedrock-secrets-config-5.png)

Finally for `clientPrivateKey`, enter the contents of the client private key (ex: `redis_user_private.key`), as shown.

![bedrock-secrets-config-6](./assets/bedrock-secrets-config-6.png)

After entering all of the Redis endpoint details, the configurations would look something like this:

![bedrock-secrets-config-7](./assets/bedrock-secrets-config-7.png)

Give your secrets a name and description.

![bedrock-secrets-config-8](./assets/bedrock-secrets-config-8.png)

Leave all of the configuration option with default values. 
![bedrock-secrets-config-9](./assets/bedrock-secrets-config-9.png)

Finally click on the `Store` button to save these secret configurations. 
![bedrock-secrets-config-10](./assets/bedrock-secrets-config-10.png)

You will be navigated back to the main UI page that enlists your secret to confirm the successful creation of the same.
![bedrock-secrets-config-11](./assets/bedrock-secrets-config-11.png)

When you click on the secrets, the details page has the ARN details that would be needed to pass it to Bedrock programatically or via a web console. 

![bedrock-secrets-config-12](./assets/bedrock-secrets-config-12.png)
