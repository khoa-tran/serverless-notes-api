# serverless-notes-api

## Deploy
Run the following:
```
serverless deploy -v
```
## Test locally
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
4) Update note: `PUT /notes/{id}`:
```javascript
{
  "body": "{\"content\":\"new world\",\"attachment\":\"new.jpg\"}",
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
- To invoke `update` function in `serverless.yml`, excute the following from the command line:
```
serverless webpack invoke --function update --path event.json
```
5) Delete note: `DELETE /notes/{id}`:
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
- To invoke `delete` function in `serverless.yml`, excute the following from the command line:
```
serverless webpack invoke --function delete --path event.json
```
