### Research Agent

The Research Agent is an AI-powered service that conducts comprehensive research and generates detailed reports based on a user-provided query. It leverages the GPT Researcher library to gather information from various sources and synthesize it into structured reports. The agent also provides a simple web interface for easy interaction.

**Main Functions:**
*   **Conduct Research:** Takes a research query and a specified report type (e.g., research report, resource report, outline report) to perform in-depth research.
*   **Generate Reports:** Produces well-structured reports, including a summary of findings, relevant sources, and associated costs.
*   **Health Check:** Provides an endpoint to verify the agent's operational status and API key configurations.
*   **Web Interface:** Serves a user-friendly HTML page to interact with the research capabilities.

**Inputs:**

*   **HTTP POST to `/research`**:
    *   `query` (string): The specific topic or question for which research is required.
    *   `report_type` (string, optional): The desired format of the report. Accepted values include `research_report` (default), `resource_report`, and `outline_report`.
*   **Environment Variables**:
    *   `OPENAI_API_KEY`: Required for accessing OpenAI's language models to process queries and generate reports.
    *   `TAVILY_API_KEY`: Required for utilizing Tavily's search capabilities to retrieve information from the web.

**Outputs:**

*   **HTTP GET from `/`**:
    *   HTML content (web page): A user interface for submitting research queries and viewing results.
*   **HTTP POST from `/research`**:
    *   JSON object: Contains the generated report, a list of source URLs, and cost details.
        *   `report` (string): The comprehensive research report, typically in Markdown format.
        *   `sources` (list of strings): URLs of the web pages or documents used as sources.
        *   `costs` (object): A dictionary detailing the estimated cost of the research (e.g., `total_cost`).
        *   `num_sources` (integer): The total number of unique sources identified and used.
*   **HTTP GET from `/health`**:
    *   JSON object: Indicates the agent's operational status and whether required API keys are configured.