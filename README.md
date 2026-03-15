# Zenodo Data Insights: Research Trend Analyzer
#### Video Demo: https://youtube.com/shorts/BASYArYWZ_Y?si=l0tv4YnSnGeKsH7Q
#### Name: Takuya Nemoto
#### GitHub: cpsbvbng26-dotcom
#### City: Utsunomiya, Japan

## Project Overview
The Zenodo Data Insights tool is a comprehensive web-based analytical application designed to interface with the Zenodo REST API. Zenodo is an open-access repository that hosts a vast array of research papers, datasets, and software. My tool allows users to query this metadata and gain immediate insights into the current landscape of academic publishing. 

The core motivation for this project is to provide a practical implementation of the "Trinity-Infinity (III∞)" framework by enabling researchers to track and visualize data across different academic disciplines. By making this information accessible and visual, the tool bridges the gap between raw metadata and actionable research trends.

## Distinctiveness and Complexity
This project stands out in several key areas of development, satisfying the rigorous requirements of the CS50x final project:

1. **API Integration and Asynchronous Requests**: The backend utilizes the Python 'requests' library to perform real-time queries against Zenodo's live API. Handling these external requests requires robust error handling to manage potential API downtime or invalid user queries.
2. **Data Transformation with Pandas**: Raw JSON data from Zenodo is often deeply nested and complex. This application uses the Pandas library to normalize and transform this data into structured DataFrames. This process is essential for cleaning the data before it can be used for any visualization.
3. **Interactive Data Visualization**: Unlike static graphs, I implemented Plotly to create interactive pie charts. This allows users to hover over segments to see specific counts and percentages, providing a deeper layer of data exploration directly in the browser.
4. **Flask Backend Architecture**: The application is built on the Flask framework, managing custom routes, form data processing, and dynamic HTML template rendering using Jinja2.

## File Structure and Functionality
- **app.py**: This is the primary controller of the application. It contains the Flask routes and the logic for calling the Zenodo API.
- **templates/index.html**: The main landing page. It features a clean search interface styled with Bootstrap 5.
- **templates/results.html**: The data dashboard that renders the Plotly chart and formatted search results.
- **static/styles.css**: Provides custom styling to ensure a professional and responsive layout.

## Design Choices and Justifications
I chose Plotly because academic data requires exploration; an interactive chart is far more effective than a static image for research purposes. I also decided to use Bootstrap 5 for the frontend to ensure the application is accessible to researchers on tablets or phones.

## How to Run the Project
Install the required libraries using 'pip install flask requests pandas plotly'. Finally, execute 'python app.py' and open your browser to the local host address.

