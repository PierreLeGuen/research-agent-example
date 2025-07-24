## Research Agent

The Research Agent is a web-based tool powered by GPT Researcher that conducts comprehensive research and generates detailed reports based on user queries. It provides a user-friendly interface to initiate research, select report types, and view the generated content, including sources and estimated costs.

### Main Functions

*   **Conducts Research**: Takes a user query and a specified report type (e.g., research, resource, outline) to perform in-depth research using AI models and external search capabilities.
*   **Generates Reports**: Produces well-structured reports based on the gathered information.
*   **Provides Sources and Costs**: Returns a list of source URLs used in the research and an estimate of the research costs.
*   **Web Interface**: Offers a simple web application for users to submit queries and view results directly in their browser.
*   **Health Check**: Includes an endpoint to verify the configuration of necessary API keys.

### Inputs

*   **Web Interface (HTTP GET /)**: Users interact via a web page served by the agent.
*   **Research Request (HTTP POST /research)**:
    *   `query` (string, required): The topic or question to research.
    *   `report_type` (string, optional, default: "research_report"): The desired format of the output report. Options include "research_report", "resource_report", or "outline_report".

### Outputs

*   **Web Interface (HTTP)**: Serves an interactive HTML page for submitting queries and displaying results.
*   **Research Report (HTTP POST /research response)**: A JSON object containing:
    *   `report` (string): The generated research report content in Markdown format.
    *   `sources` (list of strings): URLs of the sources used in the research.
    *   `costs` (object): A dictionary detailing the estimated `total_cost` (float) and `total_tokens` (integer, though currently reported as 0 by GPT Researcher).
    *   `num_sources` (integer): The total number of sources found.
*   **Health Status (HTTP GET /health response)**: A JSON object indicating the agent's `status` and whether `openai` and `tavily` API keys are `configured`.

### Environment Variables

*   **`OPENAI_API_KEY`**: Required for the GPTResearcher to function, enabling access to OpenAI's language models.
*   **`TAVILY_API_KEY`**: Required for the GPTResearcher to function, likely used for search and information retrieval through the Tavily API.