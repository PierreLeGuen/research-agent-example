# Research Agent

## Summary
The Research Agent is an AI-powered service that conducts comprehensive research and generates detailed reports based on a user-provided query. It leverages the GPT Researcher library to gather information from multiple sources and present it in a structured format.

## Functionality
*   **Conducts Research:** Takes a research query and an optional report type (e.g., research, resource, outline) to initiate a deep dive into the topic.
*   **Generates Reports:** Produces well-structured reports, including a main content section, a list of sources, and associated costs.
*   **Provides a Web Interface:** Offers a simple web-based user interface for submitting queries and viewing the generated reports directly in a browser.
*   **Exposes an API:** Provides a RESTful API endpoint for programmatic access to its research capabilities.
*   **Health Check:** Includes an endpoint to verify the service's operational status and API key configuration.

## Inputs
*   **Medium:** HTTP POST request to `/research` or via the web interface served at `/`.
*   **Parameters:**
    *   `query` (string, required): The specific topic or question to research.
    *   `report_type` (string, optional): The desired type of report. Defaults to `research_report`. Supported types include `research_report`, `resource_report`, and `outline_report`.

## Outputs
*   **Medium:** HTTP response (JSON for API, HTML for web interface).
*   **Content:**
    *   `report` (string): The comprehensive research report, typically formatted in Markdown.
    *   `sources` (list of strings): A list of URLs from which information was gathered.
    *   `costs` (object): A dictionary containing cost-related information, such as `total_cost`.
    *   `num_sources` (integer): The total number of unique sources utilized for the research.

## Environment Variables
*   **`OPENAI_API_KEY`**: Required for the underlying GPTResearcher to interact with OpenAI's language models.
*   **`TAVILY_API_KEY`**: Required for the underlying GPTResearcher to perform web searches and information retrieval using the Tavily API.