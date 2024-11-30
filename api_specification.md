# Security Risk Assessment API

## Project Description
The Security Risk Assessment API allows users to manage risk assessments effectively. Users can create, retrieve, update, and delete risk assessments, making it easier to track and manage security risks within an organization.

## API Endpoints

### 1. Create a New Risk Assessment
- **Endpoint**: `POST /api/risk-assessments`
- **Description**: Creates a new risk assessment.
- **Request Body**:
    ```json
    {
        "title": "New Risk",
        "description": "Description of the risk",
        "riskLevel": "High",
        "dateAssessed": "2024-11-30",
        "assessor": "John Doe"
    }
    ```
- **Response**:
    - **201 Created**: Risk assessment created successfully.

---

### 2. List All Risk Assessments
- **Endpoint**: `GET /api/risk-assessments`
- **Description**: Retrieves a list of all risk assessments.
- **Response**:
    - **200 OK**: Returns a list of risk assessments.

---

### 3. Retrieve a Specific Risk Assessment
- **Endpoint**: `GET /api/risk-assessments/{id}`
- **Description**: Retrieves a specific risk assessment by ID.
- **Parameters**:
    - `id` (path): The ID of the risk assessment.
- **Response**:
    - **200 OK**: Returns the risk assessment details.
    - **404 Not Found**: Risk assessment not found.

---

### 4. Update an Existing Risk Assessment
- **Endpoint**: `PUT /api/risk-assessments/{id}`
- **Description**: Updates an existing risk assessment by ID.
- **Parameters**:
    - `id` (path): The ID of the risk assessment.
- **Request Body**:
    ```json
    {
        "title": "Updated Risk",
        "description": "Updated description of the risk",
        "riskLevel": "Medium",
        "dateAssessed": "2024-12-01",
        "assessor": "Jane Doe"
    }
    ```
- **Response**:
    - **204 No Content**: Risk assessment updated successfully.
    - **404 Not Found**: Risk assessment not found.

---

### 5. Delete a Risk Assessment
- **Endpoint**: `DELETE /api/risk-assessments/{id}`
- **Description**: Deletes a risk assessment by ID.
- **Parameters**:
    - `id` (path): The ID of the risk assessment.
- **Response**:
    - **204 No Content**: Risk assessment deleted successfully.
    - **404 Not Found**: Risk assessment not found.

## Testing the API

### Using REST Client in Visual Studio Code
You can test the API using the following requests in a `.http` file:

```http
### Create a new risk assessment
POST /api/risk-assessments
Content-Type: application/json

{
    "title": "New Risk",
    "description": "Description of the risk",
    "riskLevel": "High",
    "dateAssessed": "2024-11-30",
    "assessor": "John Doe"
}

### List all risk assessments
GET /api/risk-assessments

### Retrieve a specific risk assessment
GET /api/risk-assessments/{id}

### Update an existing risk assessment
PUT /api/risk-assessments/{id}
Content-Type: application/json

{
    "title": "Updated Risk",
    "description": "Updated description of the risk",
    "riskLevel": "Medium",
    "dateAssessed": "2024-12-01",
    "assessor": "Jane Doe"
}

### Delete a risk assessment
DELETE /api/risk-assessments/{id}