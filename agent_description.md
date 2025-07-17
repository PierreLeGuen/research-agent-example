# Research Agent

The Research Agent is a web-based service powered by GPT Researcher that conducts comprehensive research and generates detailed reports based on a user-provided query. It offers an intuitive web interface for interaction and a programmatic API endpoint.

## Main Functions

*   **Conduct Research**: Takes a research query and a specified report type (e.g., research report, resource report, outline report) to gather information from various sources.
*   **Generate Reports**: Produces a structured report based on the conducted research.
*   **Source Citation**: Provides a list of URLs for the sources used in the research.
*   **Cost Tracking**: Estimates the cost associated with the research process.
*   **Health Check**: Offers an endpoint to verify the service's operational status and API key configuration.

## Inputs

*   **Medium**: HTTP POST request to `/research`
*   **Format**: JSON
*   **Details**:
    *   `query` (string, required): The specific topic or question for which research is needed.
    *   `report_type` (string, optional): The desired type of report. Defaults to "research_report". Supported types include "research_report", "resource_report", and "outline_report".

## Outputs

*   **Medium**: HTTP response (JSON for research results, HTML for the web interface)
*   **Format**: JSON
*   **Details**:
    *   `report` (string): The generated research report content, typically in Markdown format.
    *   `sources` (list of strings): A list of URLs from which information was retrieved.
    *   `costs` (object): An object containing `total_cost` (float) representing the estimated cost of the research and `total_tokens` (int).
    *   `num_sources` (int): The total number of distinct sources identified and used.

## Environment Variables

*   **`OPENAI_API_KEY`**: Required for accessing OpenAI's models, which are used by the GPTResearcher library for report generation and processing.
*   **`TAVILY_API_KEY`**: Required for accessing the Tavily API, which is used by the GPTResearcher library for search and information retrieval to gather data for the reports.