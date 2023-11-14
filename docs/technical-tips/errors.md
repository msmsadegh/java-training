# Error Handling

## Errors raise
### 5xx:
- `500`: Internal ServerError (Service Logic Disaster)
- `500`: Connection Error in Service (I don't know what happend)
- `503`: Reconnecting to Rayan. (I know what happend)

### 4xx:
- `400`: Invalid input (missing, type error input)
- `401`: no API key
- `409`: Logical error from Rayan (asset error, order error,...)
- `403`: Auth error (acl)
- `404`: url not found (maybe res is null)
- `405`: Method is not implemented


## Error Catch and Raise in API module
- ConnectionError: `requests.request` get an error
- ValueError: not 200 respons
- LookupError: can't parse content as json
