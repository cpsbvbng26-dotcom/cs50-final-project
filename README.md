cat << 'EOF' > README.md
# Zenodo Data Insights: Research Trend Analyzer
#### Video Demo: https://youtube.com/shorts/BASYArYWZ_Y?si=l0tv4YnSnGeKsH7Q
#### Name: Takuya Nemoto
#### GitHub: cpsbvbng26-dotcom
#### City: Utsunomiya, Japan

## 1. Project Description
The **Zenodo Data Insights** is a web-based data visualization and analysis tool specifically designed to interact with the Zenodo REST API. Zenodo is an open-access repository developed under the European OpenAIRE program and operated by CERN. It allows researchers to deposit research papers, data sets, software, and other research-related digital artifacts. 

The purpose of this project is to provide a streamlined, user-friendly interface for querying this vast amount of academic metadata and transforming it into meaningful visual representations. In the modern research environment, the ability to quickly grasp the distribution of knowledge—such as which languages are dominant in a specific field or what types of resources (software vs. publications) are being shared—is crucial. This tool automates the process of fetching raw JSON data from an external API, cleaning it, and rendering it as an interactive dashboard.

## 2. Distinctiveness and Complexity
This project is distinct from a basic web application or a simple CRUD app. It involves several layers of technical complexity that meet and exceed the standards of the CS50x final project:

### A. Real-time API Orchestration and Integration
Unlike many projects that rely on a local SQLite database, this application interfaces directly with a live, third-party REST API. This requires handling network requests using Python's `requests` library, managing status codes (e.g., handling 404 or 500 errors), and parsing large, multi-layered JSON objects. The application must be robust enough to handle instances where the API might be slow or return unexpected data structures.

### B. Professional Data Engineering with Pandas
The raw data returned by the Zenodo API is often deeply nested and contains irrelevant metadata for the end-user. To solve this, I utilized the **Pandas** library—a industry-standard tool for data science. The application flattens the JSON response into a structured DataFrame, performs data cleaning (such as handling missing language tags), and aggregates data to count the occurrences of specific categories. This backend data processing ensures that the visualizations are accurate and high-performance.

### C. Interactive Visualization with Plotly
Instead of using static charts, I chose to implement **Plotly**. This library allows for the creation of interactive, D3.js-based visualizations within the browser. Users can hover over segments of the charts to see precise data values, toggle categories, and export images. This choice adds significant frontend complexity, as it requires bridging Python-side data processing with JavaScript-side rendering.

### D. Scalable Flask Architecture
The backend is built using the **Flask** framework. It manages the entire lifecycle of a user’s search: from capturing the search query via a POST request, to performing the backend API calls, processing the data, and finally rendering the results using the Jinja2 templating engine. This requires a clear separation of concerns between the logic layer (app.py), the presentation layer (HTML/CSS), and the data layer (Zenodo API).

## 3. File Inventory and Functionality
- **app.py**: The central logic hub. It defines the Flask application and routes. It contains the `search` function which handles the parameters for the Zenodo API, uses Pandas to group and count the data, and generates the Plotly JSON object.
- **templates/index.html**: The landing page and search interface. It is built with Bootstrap 5 to ensure a clean, modern aesthetic and ease of use.
- **templates/results.html**: The visualization dashboard. This file contains the logic to receive the data from the backend and render it. It features a responsive layout that displays the Plotly chart alongside a detailed table of the raw search results (Title, Author, DOI).
- **static/styles.css**: A custom CSS file that extends Bootstrap's functionality. It handles the layout of the dashboard, ensuring that the charts and tables are properly aligned and that the application is fully responsive on mobile devices.
- **requirements.txt**: A critical file for project reproducibility. It lists all necessary Python dependencies (flask, requests, pandas, plotly), allowing any user to set up the identical environment with a single command.

## 4. Design Choices and Justification
- **Choice of Framework**: I chose Flask for its lightweight and flexible nature, which is ideal for a data-centric application where the focus is on API communication rather than complex database relations.
- **Visualization Library**: I chose Plotly over Matplotlib or Seaborn because interactivity is essential in a web-based tool. Researchers need to see exact numbers, which Plotly's hover-tooltips provide effortlessly.
- **UI Design**: Bootstrap 5 was selected to ensure the tool is accessible to researchers across all platforms. Whether a user is on a desktop in a lab or a smartphone in the field, the interface adapts to provide a professional experience.
- **Data Handling**: Using Pandas was a deliberate choice to allow for future scalability. While simple Python dictionaries could work for small datasets, Pandas allows the tool to handle thousands of records and perform complex statistical analysis in the future.

## 5. Instructions for Running the Project
1. Clone the repository to your environment.
2. Install the dependencies: `pip install flask requests pandas plotly`.
3. Run the server: `python app.py`.
4. Open the local address (usually http://127.0.0.1:5000) in your browser.
5. Enter any research keyword in the search bar and click 'Search' to generate the report.
EOF

