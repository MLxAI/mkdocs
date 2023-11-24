### PDF-CHAT API DOCUMENTATION

## CREATING USER SESSION

### ENDPOINT-->`/add_user_session` POST request

#### API Responses

#### USING CURL REQUESTS

#### ```curl -X 'POST' 'https://https://mlxapi-kx2ozxq4oa-uc.a.run.app/add_user_session?session_id=dummy&authentication_token=453008DJHBC743248857' -H 'accept: application/json' -d '' ```

#### USING HTTP Request URL

####  ```https://https://mlxapi-kx2ozxq4oa-uc.a.run.app/add_user_session?session_id=dummy&authentication_token=453008DJHBC743248857```

#### Response body

```
{
  "status": "true",
  "session_id": "dummy"
}
```

<br>

## UPLOADING DOCUMENTS

### ENDPOINT-->`/v1/upload` POST request

#### API Responses

#### USING CURL REQUESTS

#### ```curl -X 'POST' 'https://https://mlxapi-kx2ozxq4oa-uc.a.run.app/v1/upload?session_id=dummy&authentication_token=453008DJHBC743248857' -H 'accept: application/json' -H 'Content-Type: multipart/form-data' -F 'media_files=@test.pdf;type=application/pdf' ```

#### USING HTTP Request URL

####  ```https://https://mlxapi-kx2ozxq4oa-uc.a.run.app/v1/upload?session_id=3ds&authentication_token=453008DJHBC743248857```

#### Response body

```
{
  "status": "ready",
  "file_ids": [
    file-id1,file-id2
    ],
  "file_ids_created": [
    {
      "file-id1": "Date-created"
    },
    {
      "file-id2": "Date-created"
    }
  ],
  "doc_name": [
    "doc1.pdf",
    "doc2.pdf"
  ],
  "Purpose": "assistants"
}

```
<br>

## GETTING CHAT RESPONSES

### ENDPOINT-->`/v1/get_resp` POST request

#### API Responses

#### USING CURL REQUESTS

#### ```curl -X 'POST' \'https://https://mlxapi-kx2ozxq4oa-uc.a.run.app/v1/get_resp?session_id=3ds&file_id=[file-id1,file-id2]&question=what is this doc about?&prompt_template=You are expert in giving the answer from the given documents. Use your knowledge base to best respond to user question.&authentication_token=453008DJHBC743248857' -H 'accept: application/json' -d '' ```

#### USING HTTP Request URL

####  ```https://https://mlxapi-kx2ozxq4oa-uc.a.run.app/session_id=3ds&file_id=["file-id1","file-id2"]&question=what is this doc about?&prompt_template=You are expert in giving the answer from the given documents. Use your knowledge base to best respond to user question.&authentication_token=453008DJHBC743248857```


### Note: In this request only change session_id ,file_ids(always in str(list(str)-->["fileid-1","fileid-2"])) and question and if possible change the prompt according to usecase..

#### Response body

```
{
  
  "status": "completed",
  "output": [
    {
      "question": "user question",
      "answer": "LLM answer"
    }
  ]
}
```

