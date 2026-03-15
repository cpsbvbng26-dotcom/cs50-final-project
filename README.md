cat << 'EOF' > README.md
# Zenodo Data Insights: Research Trend Analyzer
#### Video Demo: https://youtube.com/shorts/BASYArYWZ_Y?si=l0tv4YnSnGeKsH7Q
#### Name: Takuya Nemoto
#### GitHub: cpsbvbng26-dotcom
#### City: Utsunomiya, Japan

## 1. Project Description:
The **Zenodo Data Insights** is a specialized web application developed to provide an intuitive, analytical gateway to the Zenodo REST API. Zenodo is one of the world's most significant open-access repositories, hosting a massive collection of scholarly works, datasets, and software. This project serves as a bridge, allowing users to perform complex metadata queries and instantly visualize the results to understand academic trends.

The primary motivation for this project is to create a functional tool that supports my independent research framework, **"Trinity-Infinity (III∞)"**. This framework requires the ability to track and analyze the evolution of knowledge across various domains, such as mathematics, ethics, and computer science. By quantifying and visualizing how research is distributed—whether by language, resource type, or publication date—this tool provides the empirical data necessary to support high-level academic inquiry. It transforms raw, unorganized API responses into a structured format that highlights the current state of global open-access research.

## 2. Distinctiveness and Complexity:
This project is distinct from other web-based search tools due to its specific focus on academic metadata and its integration of advanced data processing libraries. It meets the complexity requirements of CS50x through the following technical implementations:

- **Live API Orchestration**: Unlike projects that use static local databases, this application performs real-time, asynchronous communication with the Zenodo API. This requires handling dynamic queries and ensuring the application can process large JSON payloads without performance degradation.
- **Advanced Data Engineering with Pandas**: The metadata returned by Zenodo is complex and multi-layered. I utilized the **Pandas** library to "flatten" this JSON data, handle missing values, and perform data aggregation (such as counting occurrences of different languages). This level of data manipulation is typically found in data science workflows, adding a layer of complexity beyond simple web development.
- **Interactive Visual Analytics**: Instead of displaying static tables or simple Matplotlib images, I integrated **Plotly**. This allows the generation of interactive, web-based pie charts where users can hover over segments to see exact figures. This design choice was made to facilitate a deeper level of data exploration for researchers.
- **Robust Flask Integration**: The backend is built using the **Flask** framework, which manages the lifecycle of each request. It handles route definition, form data validation, and uses the Jinja2 engine to dynamically render the visualization dashboard only when data is successfully retrieved.

## 3. Detailed File Inventory:
- **app.py**: The central engine of the project. It contains the logic for defining Flask routes (`/` and `/search`). It includes the critical functions that use the `requests` library to talk to Zenodo, and the data processing pipeline that converts JSON into a Pandas DataFrame and subsequently into a Plotly-compatible JSON object.
- **templates/index.html**: The user interface for initiating searches. It uses a clean, Bootstrap 5-based design to ensure that the user can focus on the research query without distraction.
- **templates/results.html**: The dashboard for data visualization. It embeds the Plotly script and displays a dynamically generated table containing the titles, creators, and DOI links of the research papers found.
- **static/styles.css**: A custom CSS file that extends the default Bootstrap styling. It ensures that the application has a unique, professional academic aesthetic and is fully responsive across different screen sizes.
- **requirements.txt**: A configuration file listing all necessary Python packages (`flask`, `requests`, `pandas`, `plotly`), ensuring that any developer can reproduce the environment with a single command.

## 4. Design Choices and Justifications:
Every decision in the development of Zenodo Data Insights was driven by the needs of a researcher. I chose **Plotly** over other libraries because interactivity is non-negotiable in data analysis. I selected **Bootstrap 5** to ensure the tool is mobile-accessible, acknowledging that modern research often happens on the go. Furthermore, I decided to use **Pandas** for the backend logic to ensure that as the project grows, I can easily add more complex statistical features, such as regression analysis or time-series forecasting of publication trends.

## 5. Instructions for Use:
To run this application, ensure you have Python 3 installed.
1. Install the dependencies: `pip install flask requests pandas plotly`.
2. Execute the application: `python app.py`.
3. Open `http://127.0.0.1:5000` in your browser.
4. Enter a research topic (e.g., "Mathematics") to generate the insights report.
EOF
