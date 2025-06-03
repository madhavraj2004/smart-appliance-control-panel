Smart Appliance Control Panel
This project is an Admin Dashboard for managing smart appliances. It provides an interface to create, view, and remove appliances, configure their states, and interact with a backend server via RESTful API endpoints using JSON data. The interface is built with HTML and JavaScript and communicates with a backend server for appliance data storage and management.

Features
Add Appliances: Enter appliance name, description, and customizable states (Boolean, Number with limits, or List of options).
View Appliances: See all appliances currently stored on the backend server.
Delete Appliances: Remove any appliance from the backend.
Live JSON Preview: See the JSON that will be sent to the backend before submission.
RESTful API Communication: Uses fetch to POST/GET/DELETE appliance data as JSON.
Responsive UI: Usable on both desktop and smaller screens.
API Endpoints
The frontend interacts with the following backend API endpoints (hosted at http://52.250.54.24:3500/api/appliances):

1. Add Appliance
Endpoint: POST /api/appliances/store
Description: Adds a new appliance with its configuration and states.
Request Body Example:
JSON
{
  "applianceName": "Fan",
  "description": "Ceiling fan in living room",
  "appliancePrompts": [
    {
      "name": "Power",
      "description": "On/Off state",
      "type": "boolean"
    },
    {
      "name": "Speed",
      "description": "Fan speed",
      "type": "number",
      "valid_range": [1, 5]
    },
    {
      "name": "Mode",
      "description": "Fan mode",
      "type": "list",
      "valid_range": ["Normal", "Sleep", "Turbo"]
    }
  ]
}
2. Get Appliances
Endpoint: GET /api/appliances
Description: Retrieves the list of all appliances.
3. Delete Appliance
Endpoint: POST /api/appliances/delete
Description: Deletes an appliance by its _id.
Request Body Example:
JSON
{ "_id": "appliance_id_here" }
How to Test the APIs with Postman
Install Postman if you haven't already.
Set the Base URL: http://52.250.54.24:3500/api/appliances
Example: Add an Appliance
Method: POST
URL: http://52.250.54.24:3500/api/appliances/store
Headers: Content-Type: application/json
Body (raw, JSON): (see example above)
Example: Get All Appliances
Method: GET
URL: http://52.250.54.24:3500/api/appliances
Example: Delete an Appliance
Method: POST
URL: http://52.250.54.24:3500/api/appliances/delete
Headers: Content-Type: application/json
Body (raw, JSON):
JSON
{ "_id": "appliance_id_here" }
Running the Project
Clone or download the repository.
Open the HTML file (index.html or admin.html) in your browser.
Use the interface to interact with the backend via the provided API endpoints.
Technologies Used
Frontend: HTML, CSS, JavaScript
Backend (API): Expects a RESTful API (not included in this repo)
Notes
The backend server URL is currently hardcoded. Make sure the URL is correct and the API server is running.
All data exchanges are in JSON format.
For further customization or deployment, update the API endpoint URLs as needed.
