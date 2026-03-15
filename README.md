# Zenodo Data Insights: Research Trend Analyzer
#### Video Demo:
#### Description:

## Project Overview
The **Zenodo Data Insights** is a web-based analytical tool designed to interface with the Zenodo REST API. It allows researchers and academic enthusiasts to query metadata from Zenodo’s vast repository and visualize publication trends, specifically focusing on language distribution and resource types.

This project was born out of a necessity to understand the global landscape of open-access research, particularly in the fields of applied mathematics and ethics, which are central to my own research framework, "Trinity-Infinity (III∞)."

## Distinctiveness and Complexity
Unlike a simple search interface, this project integrates several layers of the CS50 curriculum:
1. **API Integration**: Utilizing the `requests` library to handle asynchronous communication with Zenodo’s backend.
2. **Data Processing**: Using `Pandas` to clean and structure raw JSON data into a manageable format.
3. **Dynamic Visualization**: Implementing `Plotly` to render interactive charts that allow users to explore data points directly in the browser.
4. **Web Framework**: A robust `Flask` application that manages routes, form submissions, and template rendering.

## File Structure
- `app.py`: The heart of the application. It handles the routing logic, API calls, and the transformation of data into Plotly-compatible JSON.
- `templates/index.html`: The landing page, designed with Bootstrap for a clean, academic aesthetic. It features a responsive search interface.
- `templates/results.html`: The visualization dashboard. It contains the logic to render Plotly charts and a filtered table of search results.
- `static/styles.css`: Custom CSS to enhance the user experience and ensure the interface remains professional and readable.
- `requirements.txt`: Lists all dependencies (`flask`, `pandas`, `plotly`, `requests`) to ensure reproducibility.

## Design Choices
During development, I chose **Plotly** over static libraries like Matplotlib because research data is meant to be explored. The ability to hover over pie segments to see exact counts provides a level of depth necessary for academic analysis. I also opted for **Bootstrap** to ensure that the tool is accessible to researchers on both mobile and desktop platforms.

## How to Run
1. Install dependencies: `pip install -r requirements.txt`
2. Start the server: `python app.py`
3. Open `http://127.0.0.1:5000` in your browser.

## Acknowledgments
This project serves as the capstone for CS50x 2026. Special thanks to the CS50 staff for providing the foundation to build tools that bridge the gap between computer science and independent academic research.
