# API Documentation: getUserId

## Description
This API endpoint retrieves the user ID associated with the provided email address.

## Endpoint
```
GET /api/getUserId
```

## Request
The API expects a JSON object with the following properties in the request body:

| Property | Type   | Required | Description            |
|----------|--------|----------|------------------------|
| email    | string | Yes      | The user's email address. |

## Response
The API returns a JSON object with the following properties in the response body:

| Property | Type   | Description                        |
|----------|--------|------------------------------------|
| userId   | string | The ID of the user associated with the provided email address. |

### Success Response
- **Status Code:** 200 OK
- **Body:**
```json
{
  "userId": "123456789"
}
```

### Error Responses
- **Status Code:** 400 Bad Request
  - **Body:**
  ```json
  {
    "message": "User id is required"
  }
  ```

- **Status Code:** 404 Not Found
  - **Body:**
  ```json
  {
    "message": "User not found"
  }
  ```

- **Status Code:** 500 Internal Server Error
  - **Body:**
  ```json
  {
    "message": "Something went wrong",
    "error": "<error message>"
  }
  ```

## Example
### Request
```
GET /api/getUserId
Content-Type: application/json

{
  "email": "user@example.com"
}
```

### Response
```
HTTP/1.1 200 OK
Content-Type: application/json

{
  "userId": "123456789"
}
```
