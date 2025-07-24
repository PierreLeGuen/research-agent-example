# Research Agent

The Research Agent is a web-based service powered by GPT Researcher designed to conduct comprehensive research and generate detailed reports on a given topic. It provides an intuitive user interface for submitting research queries and an API endpoint for programmatic access.

## Main Functions

*   **Conduct Research**: Takes a user-defined query and a specified report type (e.g., research report, resource report, outline report) to gather information from various sources.
*   **Generate Reports**: Produces well-structured research reports based on the gathered information.
*   **Source Tracking**: Identifies and lists the URLs of all sources used in the research process.
*   **Cost Estimation**: Provides an estimate of the costs associated with the research, including API usage.
*   **Health Check**: Offers an endpoint to verify the service's operational status and API key configurations.

## Inputs

*   **HTTP GET `/`**: Accesses the web-based user interface.
*   **HTTP POST `/research`**:
    *   **`query`** (string): The specific topic or question for which research is required.
    *   **`report_type`** (string, optional): The desired format of the report. Accepted values include "research_report" (default), "resource_report", and "outline_report".

## Outputs

*   **HTTP GET from `/`**: Serves an HTML page providing a user interface for research submission and display.
*   **HTTP POST from `/research`**: Returns a JSON object containing:
    *   **`report`** (string): The generated research report content.
    *   **`sources`** (list of strings): A list of URLs from which information was retrieved.
    *   **`costs`** (dictionary): Details about the research costs, including `total_cost`.
    *   **`num_sources`** (integer): The total number of unique sources found and utilized.
*   **HTTP GET from `/health`**: Returns a JSON object indicating the service's `status` and whether `openai` and `tavily` API keys are `configured`.

## Environment Variables

The agent requires the following environment variables to be set for proper functioning:

*   **`OPENAI_API_KEY`**: Your API key for accessing OpenAI services, crucial for the GPTResearcher's generative capabilities.
*   **`TAVILY_API_KEY`**: Your API key for Tavily, used by GPTResearcher for efficient search and information retrieval.