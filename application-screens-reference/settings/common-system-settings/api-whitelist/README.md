# API Whitelist

Introduction

The Lucy API operates as a RESTful web service.\
As such, all API requests can be executed in any order without dependency on the sequence.

{% hint style="info" %}
Navigate to **Settings** -> **Common System Settings** -> **API Whitelist**
{% endhint %}

Here, you will be required to specify the remote IP addresses that are permitted to communicate with the API, ensuring controlled and secure access to the service.

### Requirements

* The service exclusively utilizes JSON as the data interchange format. All responses from the API are provided in JSON, and it is expected that most request parameters are also conveyed in JSON.
* Every request made to the API must include a "Content-Type" header that is set to "application/json" to ensure proper handling and interpretation of the request data.
* All requests must be made strictly over the HTTPS protocol. Any requests sent to the API using plain HTTP will be rejected by the server.

### Authentication

Lucy API employs JWT (JSON Web Tokens) for authentication. To initiate any operations, a token must first be obtained by sending an Authentication request. This initial step is critical before proceeding with any further requests. Below are details regarding the Authentication request:

* **Obtaining the Token**: Send an Authentication request to the Lucy API. The specific details of this request, including the endpoint and required credentials (typically a username and password), are outlined in the API documentation.
* **Using the Token**: Once the token is obtained, it should be included in the "Authorization" HTTP header as part of the "Bearer" scheme for all subsequent API requests. This step is essential for authenticating your identity with the API.
* **Request Format**: All other requests, aside from the authentication request, must include this token. An example of including the token in a request header is as follows:

```json
Authorization: Bearer <your_token_here>
```

{% hint style="info" %}
The client should locally store the JWT token obtained from the authentication request and retain it until its expiration. The expiration date and time of the token are specified within the token's header, providing a clear indication of its valid usage period.&#x20;

To understand the structure of a JWT token and to access libraries for handling JWT in various programming languages, you can visit [https://jwt.io/](https://jwt.io/).
{% endhint %}

### Resources

When interacting with the Lucy API, "resources" refer to the data you either retrieve from the API or the objects you create or modify through it. The structure of these resources remains consistent, regardless of the type of action you are performing. This uniformity ensures that the representation of an object does not change whether you are fetching information about it or creating it anew.

Take "campaigns" as an example: the data structure you receive when listing all campaigns or querying a single campaign remains the same as what the server expects when you submit a request to create a new campaign. The primary distinction lies in the handling of links. During POST or PUT operations (creating or updating resources), the server does not expect any links within the request body and will ignore them if they are included. These links are utilized solely in GET requests to delineate relationships between resources.

To define relationships with other existing objects in the system, it is recommended to use integer IDs. This approach simplifies the association process between different resources within Lucy's API, ensuring clarity and consistency across various operations.

### API record Return Limit

When querying Lucy API endpoints that return a list of resources, the default behavior is to return a maximum of 100 records per request. However, if you need to retrieve more or fewer records in a single request, you can customize this by using the `LIMIT` and `OFFSET` request parameters.

The maximum number of records you can request using the `LIMIT` parameter is "1000". If you specify a `LIMIT` value greater than 1000, the API will still return a maximum of 1000 records to ensure performance and system stability. This limit ensures that the API can handle requests efficiently without compromising the server's responsiveness.

To illustrate how you can customize the number of records returned, consider the following example:

```json
GET /api/campaigns?sort=-created_at&offset=10&limit=10
```

In this example, the `sort` parameter orders the campaigns by their creation date in descending order (`-created_at`). The `offset` parameter is used to skip the first 10 records, effectively starting the list from the 11th record. The `limit` parameter then limits the number of returned records to 10. This configuration is particularly useful for implementing pagination or retrieving specific segments of data from Lucy's API.

### Example Usage

1. **Authenticate to Obtain a Token**:
   *   **Request**:

       ```json
       POST /api/auth HTTP/1.1
       Host: phish.local
       Content-Type: application/json
       Cache-Control: no-cache

       {"email":"test@test.com","password":"123"}
       ```
   *   **Response**:

       ```json
       {"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9..."}
       ```

       Use this token in the "Authorization" header for all subsequent requests.
2. **Create a Recipient Group**:
   *   **Request**:

       ```json
       PUT /api/recipient-groups/ HTTP/1.1
       Host: phish.local
       Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9...
       Content-Type: application/json
       Cache-Control: no-cache

       {"name":"test recipient group"}
       ```
   *   **Response**:

       ```json
       {"recipient-group":{"id":262,"name":"test recipient group","usb_attack":false,"links":[{"rel":"self","href":"/api/recipient-groups/262"}]}}
       ```
3. **Add a Recipient to the Group**:
   *   **Request**:

       ```json
       PUT /api/recipient-groups/262/recipients HTTP/1.1
       Host: phish.local
       Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9...
       Content-Type: application/json
       Cache-Control: no-cache

       {"email":"test@test.com","name":"Support Test"}
       ```
   *   **Response**:

       ```json
       {"recipient":{"email":"test@test.com","phone":null,"name":"Support Test"}}
       ```

This sequence demonstrates the basic operations to authenticate, create a recipient group, and add a recipient to that group within the Lucy platform using its API. Remember to replace the token, email addresses, names, and other details with your actual data when making these requests.

### Detailed Documentation and Endpoints

{% hint style="info" %}
Each Lucy server includes a Swagger client, enabling administrators to explore and test endpoints. To access the Swagger client, navigate to Settings -> Common System Settings -> API Whitelist section, and choose **API Documentation**.

![](<../../../../.gitbook/assets/image (308).png>)
{% endhint %}

A Swagger API client is a software library or tool generated from a Swagger specification, designed to facilitate communication with a web API that is described by that specification. Swagger, now known as OpenAPI, is a widely used framework for API development, offering a set of tools for designing, building, documenting, and consuming RESTful web services.
