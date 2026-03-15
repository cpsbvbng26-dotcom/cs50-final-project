cat << 'EOF' > README.md
# Zenodo Data Insights: Research Trend Analyzer
#### Video Demo: https://youtube.com/shorts/BASYArYWZ_Y?si=l0tv4YnSnGeKsH7Q
#### Name: Takuya Nemoto
#### GitHub: cpsbvbng26-dotcom
#### City: Utsunomiya, Japan

## 1. Project Overview: A Deep Dive into Academic Data Visualization
The **Zenodo Data Insights** tool is an advanced, full-stack web application designed to act as a sophisticated bridge between the Zenodo REST API and researchers who require immediate, visual feedback on academic trends. Zenodo, which is hosted by CERN as part of the European OpenAIRE program, is a massive repository for open-access research. However, accessing its metadata usually requires programming knowledge to parse complex JSON structures.

This project democratizes that data. By providing a clean, browser-based interface, any user can input a keyword—ranging from "Climate Change" to "Quantum Computing"—and receive a multifaceted dashboard. This dashboard visualizes the distribution of languages, the types of files being uploaded, and provides a direct, searchable list of DOIs (Digital Object Identifiers). This tool is essential for understanding the velocity and diversity of global research outputs in real-time.

## 2. Distinctiveness and Complexity: Why This Project is Unique
This project stands apart from common web development exercises (such as basic Task Managers or Social Media clones) due to its heavy emphasis on **Data Engineering** and **External API Orchestration**.

### A. Dynamic API Orchestration
Unlike projects that rely on static, local SQLite databases, my application handles live, unpredictable data. Using Python's `requests` library, I implemented a communication layer that manages GET requests to the Zenodo API. This involves handling query parameters, managing JSON response headers, and implementing error-catching logic for network timeouts or API service interruptions.

### B. High-Fidelity Data Processing with Pandas
The raw JSON returned by Zenodo is a "nested forest" of data. To make it usable, I integrated **Pandas**, a high-performance data manipulation library. I designed a pipeline that flattens this nested JSON into a structured DataFrame. This process includes:
1. **Data Normalization**: Converting raw API outputs into a uniform table.
2. **Missing Value Handling**: Automatically identifying and filling missing language or author tags to prevent visualization errors.
3. **Categorical Aggregation**: Grouping metadata by "Resource Type" or "Language" to generate frequency counts for the charts.

### C. Advanced Interactive Visualizations
For the frontend, I rejected static image generation in favor of **Plotly**. This choice introduced complexity in how data is passed from Python to JavaScript. The backend generates a JSON-serialized Plotly object, which is then parsed by the browser to create an interactive D3.js chart. This allows researchers to hover over data segments, zoom into specific clusters, and toggle legends on and off—features that are standard in professional data science tools but rare in student projects.

## 3. Detailed Technical File Analysis
- **app.py (The Engine)**: This file contains the core Flask logic. It manages two primary routes: the index (`/`) and the search handler (`/search`). Inside the search handler, I implemented the API call logic and the Pandas aggregation pipeline. This file acts as the controller in the MVC (Model-View-Controller) architecture, ensuring that data is correctly fetched, processed, and passed to the view.
- **templates/index.html (The Interface)**: Designed with **Bootstrap 5**, this file focuses on UX (User Experience). It features a responsive search bar and clear instructions. I used CSS Flexbox and Grid to ensure that the search input remains centered and professional across all device widths.
- **templates/results.html (The Dashboard)**: This is the most complex template. It integrates the Plotly JavaScript library. It uses Jinja2 loops to dynamically build a result table from the Pandas DataFrame, ensuring that if 10 results are found, 10 rows are rendered with their respective DOI links and metadata.
- **static/styles.css (The Aesthetic)**: To provide a professional, academic feel, I customized the Bootstrap defaults. I focused on typography and spacing, ensuring that data-heavy tables remain readable. I also implemented media queries to ensure the Plotly charts resize dynamically on mobile screens.
- **requirements.txt (The Environment)**: This file lists every dependency (`flask`, `requests`, `pandas`, `plotly`). This is crucial for "reproducibility"—a core tenet of both computer science and academic research.

## 4. Design Choices and Troubleshooting
During development, I faced a significant challenge: the Zenodo API would sometimes return 500+ results, causing the Plotly chart to become cluttered.
**The Solution**: I implemented a "Top 10" aggregation logic in the backend. By grouping smaller categories into an "Others" bucket, I ensured the visualization remained clean and informative while still representing the full scale of the data. This required a deep understanding of Pandas' `value_counts()` and slicing methods.

I also chose **Flask** over Django because of its "micro" nature. For a data-heavy application, the overhead of Django's database ORM was unnecessary, and Flask allowed me to write more explicit, readable code for the API interaction.

## 5. Future Roadmap and Scalability
This project is built with scalability in mind. The current architecture can easily be expanded to include:
1. **Multi-API Support**: Integrating the arXiv or Crossref APIs to provide a "Meta-Search" across multiple academic repositories.
2. **Export Features**: Adding a button to download the processed Pandas DataFrame as a CSV or Excel file for offline analysis.
3. **Authentication**: Implementing a user system where researchers can save their search history and track specific trends over time.

## 6. Installation and Execution Instructions
To run this project in your own environment:
1. Clone the repository: `git clone [Your Repo URL]`
2. Install dependencies: `pip install flask requests pandas plotly`
3. Launch the application: `python app.py`
4. Access the dashboard: Open your browser to `http://127.0.0.1:5000`
EOF
