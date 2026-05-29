<div align="center">

# 📈 Data Visualization Dashboard

[![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Plotly](https://img.shields.io/badge/Plotly-5.x-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)](https://plotly.com)
[![Dash](https://img.shields.io/badge/Dash-2.x-008DE4?style=for-the-badge&logo=plotly&logoColor=white)](https://dash.plotly.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

**Interactive, real-time data visualization dashboard with dynamic charts, KPIs and custom themes.**

*Built by [Abdulaziz Sadi-Cherif](https://github.com/sadidata) · SADIDATA · Paris 🇫🇷*

</div>

---

## 🚀 Overview

`data-visualization-dashboard` is a modern, interactive web dashboard built with Plotly Dash. It transforms raw data into compelling visual stories through dynamic charts, drill-down capabilities, and responsive layouts — all without leaving Python.

---

## ✨ Features

- 🌐 **Interactive Charts** — Line, bar, scatter, heatmap, treemap, and more
- - 📊 **Real-time Updates** — Live data refresh with configurable intervals
  - - 🎨 **Custom Themes** — Dark mode, light mode, and brand-color themes
    - - 📱 **Responsive Design** — Mobile-first layout with Bootstrap grid
      - - 🔧 **KPI Cards** — Configurable metric tiles with trend indicators
        - - 🔗 **Data Connectors** — CSV, API, SQL, and streaming data sources
          - - 🖨️ **Export Options** — PDF reports, PNG charts, CSV downloads
           
            - ---

            ## 📁 Project Structure

            ```
            data-visualization-dashboard/
            ├── app.py                  # Main Dash application
            ├── src/
            │   ├── layouts/
            │   │   ├── main_layout.py  # Dashboard layout
            │   │   └── sidebar.py      # Navigation sidebar
            │   ├── components/
            │   │   ├── charts.py       # Reusable chart components
            │   │   ├── kpi_cards.py    # KPI metric cards
            │   │   └── filters.py      # Filter & date range pickers
            │   ├── callbacks/
            │   │   └── update_charts.py # Dash callbacks
            │   └── data/
            │       ├── loader.py       # Data loading utilities
            │       └── processor.py    # Data processing
            ├── assets/
            │   ├── style.css           # Custom CSS
            │   └── theme.json          # Theme configuration
            ├── requirements.txt
            └── README.md
            ```

            ---

            ## 🛠️ Installation

            ```bash
            # Clone the repository
            git clone https://github.com/sadidata/data-visualization-dashboard.git
            cd data-visualization-dashboard

            # Create virtual environment
            python -m venv venv
            source venv/bin/activate  # Windows: venv\Scripts\activate

            # Install dependencies
            pip install -r requirements.txt

            # Run the dashboard
            python app.py
            ```

            Then open your browser at `http://localhost:8050`

            ---

            ## 💡 Quick Start

            ```python
            # app.py
            import dash
            from dash import html, dcc
            import plotly.express as px
            from src.data.loader import load_dataset
            from src.components.charts import create_line_chart, create_kpi_card

            app = dash.Dash(__name__, external_stylesheets=["assets/style.css"])

            # Load data
            df = load_dataset("data/sales_data.csv")

            # Build layout
            app.layout = html.Div([
                html.H1("Sales Dashboard", className="dashboard-title"),

                # KPI Row
                html.Div([
                    create_kpi_card("Total Revenue", "€2.4M", trend="+12%", color="green"),
                    create_kpi_card("Active Users", "18,432", trend="+5%", color="blue"),
                    create_kpi_card("Conversion Rate", "3.8%", trend="-0.2%", color="red"),
                ], className="kpi-row"),

                # Charts
                dcc.Graph(figure=create_line_chart(df, x="date", y="revenue")),
            ])

            if __name__ == "__main__":
                app.run(debug=True)
            ```

            ---

            ## 🎨 Dashboard Preview

            | Feature | Description |
            |---------|-------------|
            | 📊 Revenue Chart | Monthly revenue with YoY comparison |
            | 🗺️ Geographic Map | Sales distribution by region |
            | 🔥 Heatmap | Activity by day/hour |
            | 📉 Funnel Chart | Conversion funnel analysis |
            | 🎯 Scatter Plot | Customer segmentation |

            ---

            ## ⚙️ Configuration

            ```json
            {
              "theme": "dark",
              "refresh_interval": 30,
              "default_date_range": "last_30_days",
              "charts": {
                "color_palette": ["#00B4D8", "#0077B6", "#023E8A"],
                "animation": true,
                "hover_mode": "unified"
              },
              "kpi_cards": {
                "show_trend": true,
                "trend_period": "vs last month"
              }
            }
            ```

            ---

            ## 📦 Requirements

            ```
            dash>=2.14.0
            plotly>=5.18.0
            pandas>=2.0.0
            numpy>=1.24.0
            dash-bootstrap-components>=1.5.0
            gunicorn>=21.0.0
            python-dotenv>=1.0.0
            ```

            ---

            ## 🚢 Deployment

            ```bash
            # Deploy with Gunicorn
            gunicorn app:server -b 0.0.0.0:8050

            # Or with Docker
            docker build -t viz-dashboard .
            docker run -p 8050:8050 viz-dashboard
            ```

            ---

            ## 🤝 Contributing

            Contributions are welcome! Please feel free to submit a Pull Request.

            1. Fork the project
            2. 2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
               3. 3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
                  4. 4. Push to the branch (`git push origin feature/AmazingFeature`)
                     5. 5. Open a Pull Request
                       
                        6. ---
                       
                        7. ## 📄 License
                       
                        8. This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
                       
                        9. ---
                       
                        10. <div align="center">

                        Made with ❤️ by **Abdulaziz Sadi-Cherif** | [GitHub](https://github.com/sadidata) | [Email](mailto:sadidataconseil@gmail.com)

                        </div>
