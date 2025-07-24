# Research Agent

## Summary
A research agent powered by GPT Researcher that conducts comprehensive research and generates reports based on a given query. It provides a web interface for users to initiate research and view results.

## Functionality
This agent operates as a web service, allowing users to:
*   **Initiate Research:** Submit a research query and specify the desired report type (e.g., research, resource, outline report).
*   **Generate Reports:** Produce detailed research reports, including content, sources, and cost estimates, by leveraging the GPT Researcher library.
*   **Access Web Interface:** Interact with the agent through a simple web-based user interface served directly by the agent.
*   **Health Check:** Verify the operational status of the agent and the configuration of required API keys.

## Inputs
*   **HTTP GET `/`**: Accesses the agent's web interface.
*   **HTTP POST `/research` (JSON)**: Initiates a research task.
    *   `query` (string, required): The topic or question for the research.
    *   `report_type` (string, optional): Specifies the type of report to generate. Defaults to "research_report". Supported types include "research_report", "resource_report", and "outline_report".

## Outputs
*   **HTTP GET `/` (HTML)**: Serves the `index.html` file, providing the user interface.
*   **HTTP POST `/research` (JSON)**: Returns the research results.
    *   `report` (string): The generated research report content in Markdown format.
    *   `sources` (list of strings): A list of URLs for the sources used in the research.
    *   `costs` (dictionary): Contains cost-related information, including `total_cost` (float) and `total_tokens` (integer).
    *   `num_sources` (integer): The total number of unique sources identified.
*   **HTTP GET `/health` (JSON)**: Provides the agent's health status.
    *   `status` (string): Indicates "healthy" if the agent is running.
    *   `api_keys_configured` (dictionary): Shows the configuration status of `openai` and `tavily` API keys (boolean).

## Environment Variables
*   **`OPENAI_API_KEY`**: Your OpenAI API key, essential for the GPT Researcher to utilize OpenAI's models for generating research content.
*   **`TAVILY_API_KEY`**: Your Tavily API key, required for the GPT Researcher to perform web searches and retrieve information.