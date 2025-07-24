### Research Agent

The Research Agent is a web-based service powered by GPT Researcher that conducts comprehensive research and generates detailed reports based on user queries. It provides a user-friendly interface to initiate research and view results.

**Main Functions:**
*   **Conduct Research:** Takes a user query and a specified report type (e.g., research report, resource report, outline report) to perform in-depth research.
*   **Generate Reports:** Produces structured research reports, including key findings, supporting sources, and estimated costs.
*   **Serve Web Interface:** Provides an interactive web application for users to input queries and display research outcomes.
*   **Health Check:** Offers an endpoint to verify the operational status of the agent and the configuration of required API keys.

**Inputs:**
*   **HTTP (Web Interface):** Users interact via a web page (`/`) to submit research queries and select report types.
*   **HTTP (API Endpoint):** A POST request to `/research` with a JSON body containing:
    *   `query` (string): The topic or question for research.
    *   `report_type` (string, optional, default: "research_report"): The desired format of the research report (e.g., "research_report", "resource_report", "outline_report").
*   **Environment Variables:**
    *   `OPENAI_API_KEY`: Required for accessing OpenAI's language model capabilities.
    *   `TAVILY_API_KEY`: Required for search and information retrieval.

**Outputs:**
*   **HTTP (Web Interface):** Serves an HTML page (`static/index.html`) for the user interface.
*   **HTTP (API Endpoint):** A JSON response from `/research` containing:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs or identifiers for the sources used.
    *   `costs` (dict): Information about the cost of the research (e.g., total cost).
    *   `num_sources` (int): The total number of sources identified.
*   **HTTP (API Endpoint):** A JSON response from `/health` indicating the agent's status and API key configuration.