### Research Agent

The Research Agent is an AI-powered service that conducts comprehensive research and generates detailed reports based on a user-provided query. It leverages the GPT Researcher library to gather information from various sources and synthesize it into structured reports.

**Main Functions:**

*   **Conduct Research**: Generates in-depth research reports, resource reports, or outline reports on any given topic.
*   **Source Citation**: Provides a list of sources used to compile the report.
*   **Cost Estimation**: Estimates the cost associated with the research process.
*   **Health Check**: Offers an endpoint to verify the service's operational status and API key configurations.
*   **User Interface**: Provides a simple web interface for users to submit research queries and view results.

**Inputs:**

*   **HTTP POST to `/research`**:
    *   `query` (string): The research topic or question.
    *   `report_type` (string, optional): The desired type of report (e.g., "research_report", "resource_report", "outline_report"). Defaults to "research_report".

**Outputs:**

*   **HTTP Response from `/research`**:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs or identifiers for the sources used.
    *   `costs` (dictionary): Details about the research cost, including `total_cost` and `total_tokens`.
    *   `num_sources` (integer): The total number of research sources found.
*   **HTTP Response from `/`**: A web-based user interface (`index.html`) for interacting with the agent.

**Environment Variables:**

*   `OPENAI_API_KEY`: Required for accessing OpenAI's language models, which are central to the GPT Researcher's functionality.
*   `TAVILY_API_KEY`: Required for using Tavily's search API, which is crucial for information retrieval during the research process.