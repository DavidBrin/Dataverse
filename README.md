## Flask Application Design

### HTML Files

#### 1. index.html (Dashboard)

- Purpose: Main HTML file serving as the landing page and dashboard of the web application.
- Content:
  - Navigation bar for accessing different sections of the application.
  - Header section displaying the application's title and logo.
  - Main dashboard content area:
    - Tabs or sections for different sensor types, e.g., temperature, humidity, pressure.
    - Real-time display of mock data (placeholder values) for each sensor type.
    - Functionality to receive and display real-time data from the space satellite when available.
  - Footer section providing additional information, copyright notices, etc.

#### 2. register.html (Cargo Container Registration)

- Purpose: HTML file for registering cargo containers.
- Content:
  - Form for users to provide information about their cargo containers:
    - Name of the container.
    - Type of cargo (e.g., perishable, hazardous, standard).
    - Destination of the container.
  - Submit button to send the registration data to the server.

#### 3. data.html (Real-Time Data Display)

- Purpose: HTML file for displaying real-time data from the cargo containers.
- Content:
  - Table or other suitable visual elements for presenting the data received from the satellite.
  - Functionality to periodically refresh the displayed data, fetching the latest readings from the sensors.
  - Each row of the table should contain real-time readings from the sensors associated with a cargo container.

### Routes

#### 1. Route to Register Cargo Containers

- Endpoint: `/register`
- Method: POST
- Purpose: Accepts information about the cargo containers from the registration form (index.html) and stores it in a database or other suitable storage mechanism.
- Functionality:
  - Validate the received data for completeness and correctness (e.g., checking for empty fields or invalid input formats).
  - Insert the validated data into a database table or other persistent storage.
  - Return an appropriate response to the client (e.g., success message or error message).

#### 2. Route to Retrieve Real-Time Data

- Endpoint: `/data`
- Method: GET
- Purpose: Returns the real-time data collected from the space satellite. The route is called periodically by the client (index.html) to update the displayed data.
- Functionality:
  - Query the database or other data source to retrieve the latest readings from the sensors associated with the cargo containers.
  - Format the data in a JSON or other suitable format for transmission to the client.
  - Return the formatted data as a response to the client.

#### 3. Route to Display Dashboard

- Endpoint: `/dashboard`
- Method: GET
- Purpose: Serves the dashboard page (index.html) to the user.
- Functionality:
  - Simply return the index.html file, as it contains all the HTML code necessary for the dashboard.
  - This route is typically accessed when the user first opens the web application or navigates to the dashboard section.

This Flask application design provides a clear structure for managing cargo container registration, displaying real-time data, and serving the dashboard interface. It leverages Flask's routing capabilities and allows for easy interaction between the client (HTML files) and the server (Flask application).