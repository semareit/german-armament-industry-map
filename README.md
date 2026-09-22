# german-armament-industry-map

Standorte der deutschen Waffen- und Rüstungsindustrie

## Description

This project creates an interactive web map of german armament industry, displaying locations of defense contractors from the country.
It uses Leaflet.js, a lightweight and open-source JavaScript library for mobile-friendly interactive maps.
It uses OpenStreetMap as map layer.
The language of contents in this mockup is mostly german.

## Features

**companies.json**: The file is an array of objects. Each object represents a company and contains:

- `name`: The name of the company.
- `description`: A short text description of the company.
- `url`: A link to company website.
- `category`: An array of strings listing the main categories of or main activity fields.
- `parents`: An array of strings listing the id of parent companies.
- `products`: An array of strings listing the main defense products or services.

**sites.json**: The file is an array of objects. Each object represents a company site and contains:

- `id`: A unique identifier.
- `companyId`: The id of the company the a site belongs too.
- `siteName`: The name of the company site.
- `headquarter`: A flag that indicats the headquarter site.
- `description`: A short text description of the company site.
- `lat`: The latidude coordinate of location.
- `lng`: The longitude coordinate of location.
- `address`: The address of the site location.
- `city`: The city of the site location.
- `country`: The country of the site location.
- `products`: An array of strings listing the main products or services of the site location.
- `sources`: An array of strings listing the sources of information for the site location entry.

**index.html**: The main HTML file that:

- The HTML file uses the Leaflet library (loaded via CDN) to render the map. 
- It fetches the JSON data using the fetch API, iterates through the companies, and places a marker on the map for each set of coordinates.
- Clicking a marker displays a popup with the company’s details.

## Prerequisites

- A modern web browser.
- A local web server (e.g., VS Code Live Server, Python http.server, or Node http-server or live-server) is recommended to avoid CORS issues when loading the JSON file.

  > Note: For Security reasons, browser do not allow open local JSON-Files directly via fetch. Therefore a light local web server is required.

## How to Run

1. Place **companies.json**, **sites.json** and **index.html** in the same directory.

   > Note: For Security reasons, browser do not allow open local JSON-Files
   > directly via fetch. Therefore a light local webserver is required.

2. Open a terminal in the same directory.
3. Start local web server via terminal.
4. Open web browser and goto url.

## Local Webserver with Python http.server

**1. Prerequisites:**

- Python 3 is installed on your system.
- You can check this by running:

  ```bash
  python3 -V
  ```

**2. Start the Server:**

   ```plaintext
   python3 -m http.server 8000 --bind 0.0.0.0
   ```
  
   > Remark:
   > `127.0.0.1` binds only to localhost interface (only accessible from same device).
   > `0.0.0.0` binds all network interfaces (accessible from remote devices – attention with firewalls!, open related port).

**3. Access page in browser:**

- Then visit `http://<your-ip-address>:8000`.

**4. Stopping the Server:**
Press `Ctrl` + `C` in the terminal to stop the server.

## Local Webserver with Node.js live-server

**1. Prerequisites:**

- Node.js and npm installed on your system.
- You can check this by running:

  ```bash
  node -v
  npm -v
  ```

**2. Install Live-Server:**

- install it locally in your project directory (recommended for team projects):

  ```bash
  cd /path/to/your/project
  npm install live-server
  ```

**3. Start the Server:**

- If you installed live-server locally, add a script to your `package.json`:

  ```json
  {
    "scripts": {
      "start": "live-server",
      "dev": "live-server --port=8000 --open=."
    }
  }
  ```

- Then start the server with:
  
  ```bash
  npm start
  # or
  npm run dev
  ```

- Useful Command-Line Options:

  - `--port`: Change the port number. Example: `live-server --port=3000`
  - `--host`: Bind to a specific IP. Example: `live-server --host=0.0.0.0`
  - `--root`: Set a custom root directory. Example: `live-server --root=docs`
  - `--open`: Open a specific file or directory. Example: `
live-server --open=docs/index.html`
  - `--browser`: Specify a browser. Example: `live-server --browser=chrome`
  - `--no-css-inject`: Disable CSS live reload. `live-server --no-css-inject`

**4. Access page in browser:**

- Then visit `http://<your-ip-address>:8000`.

**5. Stopping the Server:**
Press `Ctrl` + `C` in the terminal to stop the server.
