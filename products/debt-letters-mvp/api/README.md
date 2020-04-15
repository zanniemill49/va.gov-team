# Debt Letters MVP API

*Last Updated April 14, 2020*

## Endpoints

| HTTP Method | Endpoint                          | Description                                                                                                                         |
|-------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| GET         | /v0/debt_letters                  | Get a list of all debt letters for a particular veteran.                                                                            |
| GET         | /v0/debt_letters/{ id }           | Get details on a particular debt letter.                                                                                            |
| POST        | /v0/debt_letters/notifications    | Triggers a notification to be created and an email to be sent out to the veteran, letting them know a new debt letter is available. |

### GET /v0/debt_letters

#### Example Request

```
GET https://api.va.gov/v0/debt_letters
```

#### Example Response

```json
HTTP/1.1 200 OK
Date: Thu, Jan 30 2020 21:30:42 GMT
Transfer-Encoding: chunked
Content-Type: application/json

{
  "data": [
    {
      "id": "9fbc9cfa-9bd6-4eb5-a24d-98ef0c198eb3",
      
    }
  ]
}
```

### GET /v0/debt_letters/:id

#### Example Request

#### Example Response

### POST /v0/debt_letters/notifications

#### Example Request

#### Example Response
