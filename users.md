- [Login a user](#login) `POST /api/users/login`
- [Register a user](#register) `POST /api/users/register`
- [Confirm email](#confirmemail) `POST /api/users/confirmemail`
- [Reset password](#resetpassword) `POST /api/users/resetpassword`
- [Confirm reset password](#confirmpassword) `POST /api/users/confirmpassword`
- [Update and return updated user](#update) `POST /api/users/update`
- [Read and return a user](#read) `POST /api/users/read`
- [Query and return users](#query) `POST /api/users/query`

---

<h2 id="login"> Login </h2>

**Login a user**

**URL** : `/api/users/login`

**Method** : `POST`

**Authentication** : `Logged out`

**Data Constraints**

```json
{
  "email": "(STRING - REQUIRED) The email of the user",
  "password": "(STRING - REQUIRED) The unhashed password of the user",
  "sessionId": "(STRING - OPTIONAL) The current session id"
}
```

**Response Code**
`200: OK`
`400: Argument Validation Errors`
`400: User not found`
`401: Unauthorized`
`500: Database Error`

**Success Response**

```json
{
  "status": "200",
  "response": {
    "id": "1",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
  }
}
```

**Error Response**

```json
{
  "status": "400",
  "response": {
    "error": "Invalid email/password"
  }
}

{
  "status": "400",
  "response": {
    "error": "User not found"
  }
}

{
  "status": "401",
  "response": {
    "error": "Already logged in"
  }
}

{
  "status": "500",
  "response": {
    "error": "Mybatis error"
  }
}
```

---

<h2 id="register"> Register </h2>

**Register a user**

**URL** : `/api/users/register`

**Method** : `POST`

**Authentication** : `Logged out`

**Data Constraints**

```json
{
  "name": "(STRING - REQUIRED) The name of the new user",
  "email": "(STRING - REQUIRED) The email of the user",
  "phone": "(STRING - REQUIRED) The phone of the user",
  "password1": "(STRING - REQUIRED) The unhashed password1 of the user",
  "password2": "(STRING - REQUIRED) The unhashed password2 of the user"
}
```

**Response Code**
`200: OK`
`400: Argument Validation Errors`
`400: User already exists`
`401: Unauthorized`
`500: Database Error`

**Success Response**

```json
{
  "status": "200",
  "response": {
    "id": "1",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
  }
}
```

**Error Response**

```json
{
  "status": "400",
  "response": {
    "error": "Invalid email/password"
  }
}

{
  "status": "400",
  "response": {
    "error": "User already exists"
  }
}

{
  "status": "401",
  "response": {
    "error": "Already logged in"
  }
}

{
  "status": "500",
  "response": {
    "error": "Mybatis error"
  }
}
```

---
