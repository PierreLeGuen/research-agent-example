### Research Agent

**Summary:**
A research agent powered by GPT Researcher that conducts comprehensive research and generates reports based on a given query.

**Key Features:**
*   **Comprehensive Research:** Conducts in-depth research on a specified topic using the GPT Researcher library.
*   **Report Generation:** Generates various types of reports, including research reports, resource reports, and outline reports.
*   **Source Citation:** Provides a list of sources used during the research process.
*   **Cost Estimation:** Estimates the cost of the research operation.
*   **Web Interface:** Offers a user-friendly web interface for submitting research queries and viewing results.
*   **API Endpoint:** Exposes a programmatic API endpoint for research requests.

**Inputs:**
*   **Web Interface (HTTP GET /):** Users interact via a web page to submit queries.
*   **Research Request (HTTP POST /research):**
    *   `query` (string): The topic or question to research.
    *   `report_type` (string, optional): The desired type of report (e.g., "research_report", "resource_report", "outline_report"). Defaults to "research_report".

**Outputs:**
*   **Web Page (HTTP GET /):** Serves an interactive HTML page for research submission and display.
*   **Research Report (HTTP POST /research):** Returns a JSON object containing:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): URLs of the sources cited in the report.
    *   `costs` (dictionary): Estimated costs of the research, including `total_cost` and `total_tokens`.
    *   `num_sources` (integer): The total number of unique sources found.
*   **Health Check (HTTP GET /health):** Returns a JSON object indicating the service status and whether required API keys are configured.

**Prerequisites:**
*   **`OPENAI_API_KEY`**: An OpenAI API key is required for the agent to function.
*   **`TAVILY_API_KEY`**: A Tavily API key is required for search and information retrieval.