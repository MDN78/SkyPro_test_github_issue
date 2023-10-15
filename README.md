# How to work with GitHub issue vs Postman:
## Step 1 - generate new token
1) Create API token i-n your Githup profile </br> `Settings -> Deleloper settings -> Personal access token -> Token classics`
2) Turn button</br> `Generate new token `
3) Take a name of key, Assigne permissions
4) Press button `Generate token`
## Step 2 - Postman
1) Create new Postman collection
2) Select `Authorization -> Type -> Bearer Token `
3) Input your token from Github and save changes
## Step 2 - Methods
[General GitHub REST API docs](https://docs.github.com/en/rest/issues/issues?apiVersion=2022-11-28#about-issues)
### GET for get information about issues list
- PATH: - `https://api.github.com/repos/{owner}/{repo}/issues`
- Authorization: - `inherit auth from parent`
### POST for creating new issue
- PATH: - `https://api.github.com/repos/{owner}/{repo}/issues`
- Authorization: - `inherit auth from parent`
- Body:</br> 
```
{
    "title": "ussue_1",
    "body": "Something went wrong",
    "assignee": "MDN78",
    "labels": [
        "bug"
    ]
}
```

- Test, Script for getting issue number 
```
var key = "issue_number"
var value = pm.response.json().number
pm.collectionVariables.set(key, value);
```
### PATCH - for update issue
- PATH: - `https://api.github.com/repos/{owner}/{repo}/issues/{issue_number}`
- Body (example):
```
{
    "title": "new title name"
}
```


