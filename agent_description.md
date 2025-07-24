# Research Agent

The Research Agent is an AI-powered service that conducts comprehensive research and generates detailed reports based on user queries. It leverages the GPT Researcher library to gather information from various sources and synthesize it into structured reports. The agent provides a web-based user interface for easy interaction and an API for programmatic access.

## Main Functions

*   **Conduct Research**: Takes a user-defined query and a specified report type (e.g., research, resource, outline) to perform in-depth research.
*   **Generate Reports**: Produces well-structured research reports, including key findings, supporting details, and source attribution.
*   **Source Tracking**: Identifies and lists the URLs of all sources used during the research process.
*   **Cost Estimation**: Provides an estimate of the costs associated with the research, based on API usage.
*   **Health Check**: Offers an endpoint to verify the operational status of the agent and the configuration of required API keys.

## Inputs

*   **Medium**: HTTP POST request
*   **Endpoint**: `/research`
*   **Content**: JSON payload with the following fields:
    *   `query` (string, required): The research topic or question.
    *   `report_type` (string, optional): The desired type of report. Defaults to `research_report`. Supported types include `research_report`, `resource_report`, and `outline_report`.

## Outputs

*   **Medium**: HTTP Response (JSON or HTML)
*   **Endpoint `/research`**:
    *   **Content**: JSON payload containing the research results:
        *   `report` (string): The generated research report in Markdown format.
        *   `sources` (list of strings): A list of URLs from which information was gathered.
        *   `costs` (dict): A dictionary detailing the estimated cost of the research (e.g., `total_cost`).
        *   `num_sources` (int): The total number of sources identified.
*   **Endpoint `/`**:
    *   **Content**: HTML page providing a user interface to interact with the research agent.
*   **Endpoint `/health`**:
    *   **Content**: JSON payload indicating the agent's status and whether required API keys are configured.

## Prerequisites

This agent requires the following environment variables to be configured for proper operation:

*   `OPENAI_API_KEY`: Your API key for accessing OpenAI's language models.
*   `TAVILY_API_KEY`: Your API key for using the Tavily search API, essential for information retrieval.