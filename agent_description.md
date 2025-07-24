### Research Agent

The Research Agent is an AI-powered service that conducts comprehensive research and generates detailed reports based on user queries. It leverages the GPT Researcher library to gather information from various sources and synthesize it into a coherent report.

**Main Functions:**

*   **Conduct Research**: Takes a user-defined query and a specified report type (e.g., research, resource, or outline report) to perform in-depth research. It then generates a structured report, lists the sources used, and provides an estimated cost of the research.
*   **Web Interface**: Provides a simple web-based user interface for submitting research queries and viewing the generated reports directly in a browser.
*   **Health Check**: Offers an endpoint to verify the agent's operational status and confirm the configuration of necessary API keys.

**Inputs:**

*   **HTTP POST to `/research`**:
    *   `query` (string): The topic or question to research.
    *   `report_type` (string, optional): The desired type of report. Options include "research_report" (default), "resource_report", and "outline_report".

**Outputs:**

*   **HTTP JSON Response from `/research`**:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs or identifiers for the sources used in the research.
    *   `costs` (dict): Information about the cost of the research, including `total_cost` and `total_tokens`.
    *   `num_sources` (int): The total number of distinct research sources found.
*   **HTTP HTML Response from `/`**:
    *   A user-friendly web interface for interacting with the agent.

**Environment Variables:**

*   `OPENAI_API_KEY`: Required for the GPTResearcher to function, enabling interactions with the OpenAI API for text generation and understanding.
*   `TAVILY_API_KEY`: Required for the GPTResearcher to perform search and information retrieval from Tavily's search API.