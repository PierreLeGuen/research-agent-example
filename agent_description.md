### Research Agent

The Research Agent is a web-based application designed to conduct comprehensive research and generate detailed reports on various topics. It leverages advanced AI models and search capabilities to gather information from multiple sources and synthesize it into structured reports.

#### Main Functions

*   **Conduct Research**: Generates in-depth research reports, resource reports, or outline reports based on a user-provided query.
*   **Source Gathering**: Identifies and lists the URLs of all sources used in the research process.
*   **Cost Tracking**: Provides an estimate of the research cost.
*   **Health Check**: Offers an endpoint to verify the operational status of the agent and the configuration of required API keys.
*   **User Interface**: Provides a simple web interface for users to submit research queries and view results.

#### Inputs

*   **HTTP POST /research**
    *   `query` (string): The specific question or topic for which research is needed.
    *   `report_type` (string, optional): The desired format of the output report. Options include "research_report" (default), "resource_report", and "outline_report".

#### Outputs

*   **HTTP GET /**
    *   Serves an interactive HTML web page, allowing users to submit research requests and view generated reports directly in their browser.
*   **HTTP POST /research**
    *   Returns a JSON object containing:
        *   `report` (string): The generated research report content in Markdown format.
        *   `sources` (list of strings): A list of URLs that were used as sources for the report.
        *   `costs` (dictionary): Details about the cost incurred during the research, including `total_cost` and `total_tokens`.
        *   `num_sources` (integer): The total count of unique sources utilized.
*   **HTTP GET /health**
    *   Returns a JSON object indicating the service `status` and whether the necessary `api_keys_configured` are set.

#### Environment Variables

The agent requires the following environment variables to be configured:

*   `OPENAI_API_KEY`: Your API key for accessing OpenAI services, essential for language model interactions.
*   `TAVILY_API_KEY`: Your API key for accessing Tavily's search capabilities, crucial for information gathering.