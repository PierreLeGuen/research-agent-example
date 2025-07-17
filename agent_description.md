### Research Agent

The Research Agent is a web-based service powered by GPT Researcher designed to conduct comprehensive research and generate detailed reports on specified topics. It provides an API endpoint for initiating research and a user-friendly web interface for interaction.

**Main Functions:**

*   **Conduct Research**: Takes a user query and a desired report type (e.g., research report, resource report, outline report) to perform in-depth research using external APIs.
*   **Generate Reports**: Produces a structured report based on the gathered information.
*   **Provide Sources and Costs**: Returns the URLs of the sources used for research and an estimate of the associated operational costs.
*   **Health Check**: Offers an endpoint to verify the agent's operational status and API key configurations.

**Inputs:**

*   **HTTP POST to `/research`**:
    *   **Medium**: HTTP JSON
    *   **Parameters**:
        *   `query` (string, required): The topic or question for which research is to be conducted.
        *   `report_type` (string, optional, default: "research_report"): The type of report to generate. Supported types include "research_report", "resource_report", and "outline_report".

**Outputs:**

*   **HTTP JSON from `/research`**:
    *   **Medium**: HTTP JSON
    *   **Content**:
        *   `report` (string): The generated research report content.
        *   `sources` (list of strings): A list of URLs from which information was retrieved.
        *   `costs` (object): A dictionary containing cost-related information, including `total_cost` (float) and `total_tokens` (integer).
        *   `num_sources` (integer): The total number of distinct sources used.
*   **Web Interface from `/`**:
    *   **Medium**: HTTP HTML
    *   **Content**: A user interface allowing users to input research queries and view the generated reports.

**Environment Variables:**

*   **`OPENAI_API_KEY`**: Your OpenAI API key, essential for the underlying large language model operations.
*   **`TAVILY_API_KEY`**: Your Tavily API key, used for search and information retrieval during the research process.