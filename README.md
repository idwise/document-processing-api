# IDWise Document Processing API

Integrating with IDWise document processing API couldn’t be easier! It is a standard HTTP API, it processes a document and optionally a selfie and returns the recognition and information extraction results synchronously as part of the HTTP response as JSON.

You can access this API by integrating to a simple app, or simply by invoking it using a tool such as Postman.



* **API endpoint:** [https://api.idwise.com/process/document](https://api.idwise.com/process/document)
* **Authentication:** Basic authentication

    With a base64 encoded API key (as username) and API secret (use as password) separated by a colon (:) in the "authorization" HTTP header, API Key and API Secret will be shared separately.

* **HTTP Method**: POST
* **POST Body**: Encoded as form-data (multi-part).
* **Parameters:**
    * **front (or image)**: of type "file", this should include the image file to be processed, the image can be of any widely used image format (JPG, PNG, ...)
    * **back**: this parameter is optional, and can be used to process a double-sided document.
* **Example **on how to invoke the API via (curl) command-line tool, you need to add the full authentication header:


```
curl --location --request POST 'https://api.idwise.com/process/document' \
--header 'Authorization: Basic YmN..........DRi' --form 'front=@"/C:/my-image.jpg"'
