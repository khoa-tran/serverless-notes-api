# serverless-notes-api
- Create an `event.json` file and add the following:
```javascript
{
  "body": "{\"content\":\"hello world\",\"attachment\":\"hello.jpg\"}",
  "requestContext": {
    "authorizer": {
      "claims": {
        "sub": "USER-SUB-1234"
      }
    }
  }
}
```
- To invoke `create` function in `serverless.yml`, excute the following from the command line:
```
serverless webpack invoke --function create --path event.json
```
