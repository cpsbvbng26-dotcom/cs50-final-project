cat << 'EOF' > README.md
# Zenodo Data Insights: Research Trend Analyzer
#### Video Demo: https://youtube.com/shorts/BASYArYWZ_Y?si=l0tv4YnSnGeKsH7Q
#### Name: Takuya Nemoto
#### GitHub: cpsbvbng26-dotcom
#### City: Utsunomiya, Japan

## Description:
This project is an advanced, web-based analytical application designed to interface with the Zenodo REST API. Zenodo is a critical open-access repository that hosts an immense volume of research papers and datasets. My application allows users to query this metadata and extract real-time insights into the global landscape of academic publishing. 

The fundamental motivation for this project is to create a practical tool that embodies the principles of my "Trinity-Infinity (III∞)" research framework. By enabling researchers to efficiently track, visualize, and analyze academic trends across a multitude of disciplines, this tool bridges the gap between raw metadata and actionable research intelligence. It empowers independent researchers to identify emerging fields of study and the distribution of knowledge across different languages and media types.

## Distinctiveness and Complexity:
This project satisfies and exceeds the CS50x requirements through its technical complexities:
1. **API Integration**: It performs dynamic, real-time queries against Zenodo’s live REST API using Python's 'requests' library, including robust error handling.
2. **Data Engineering**: It leverages the 'Pandas' library to clean and transform raw JSON responses into structured DataFrames.
3. **Data Visualization**: It implements interactive 'Plotly' charts, allowing users to explore data points directly in the browser.
4. **Flask Architecture**: The backend is built with Flask, managing routes, form processing, and Jinja2 template rendering.

## File Structure:
- **app.py**: The main controller for API logic and routing.
- **templates/index.html**: The search interface styled with Bootstrap 5.
- **templates/results.html**: The dashboard for visualizations and results.
- **static/styles.css**: Custom styles for a responsive, academic aesthetic.
- **requirements.txt**: Lists dependencies like flask, requests, pandas, and plotly.

## Design Choices:
I chose Plotly because academic data requires exploration; an interactive chart is far more effective than a static image. I used Bootstrap 5 for a mobile-first experience, ensuring accessibility for researchers on any device.
EOF
