# Direct methods to IoT Edge Module with Python Example

```python

#handler
async  def  method1_listener(module_client):
	while  True:
	method_request = await module_client.receive_method_request("method1") # Wait for method1 calls
	print("Message received : %s " % method_request.payload)

	payload = {"result": True, "data": "some data"} # set response payload
	status = 200  # set return status code
	print("executed method1")
	method_response = MethodResponse.create_from_method_request(method_request, status, payload)

	await module_client.send_method_response(method_response) # send response

```

