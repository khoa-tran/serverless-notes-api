# serverless-notes-api
1) Create new note: `POST /notes`:
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
2) Get note: `GET /notes/{id}`:
```javascript
{
  "pathParameters": {
    "id": "578eb840-f70f-11e6-9d1a-1359b3b22944"
  },
  "requestContext": {
    "authorizer": {
      "claims": {
        "sub": "USER-SUB-1234"
      }
    }
  }
}
```
- To invoke `get` function in `serverless.yml`, excute the following from the command line:
```
serverless webpack invoke --function get --path event.json
```
3) Get all notes: `GET /notes`:
```javascript
{
  "requestContext": {
    "authorizer": {
      "claims": {
        "sub": "USER-SUB-1234"
      }
    }
  }
}
```
- To invoke `list` function in `serverless.yml`, excute the following from the command line:
```
serverless webpack invoke --function list --path event.json
```
