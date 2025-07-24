### Research Agent

The Research Agent is an AI-powered service that conducts comprehensive research and generates detailed reports based on a user-provided query. It leverages the GPT Researcher library to gather information from various sources and synthesize it into structured reports.

#### Functionality

*   **Conduct Research**: Takes a research query and a desired report type (e.g., "research\_report", "resource\_report", "outline\_report").
*   **Generate Reports**: Produces a comprehensive report based on the conducted research.
*   **Source Tracking**: Provides a list of sources used during the research process.
*   **Cost Estimation**: Estimates the cost associated with the research, including total cost and token usage.
*   **Health Check**: Offers an endpoint to verify the agent's operational status and API key configurations.

#### Inputs

*   **HTTP POST Request to `/research`**:
    *   `query` (string): The research topic or question.
    *   `report_type` (string, optional): The type of report to generate (default: "research\_report").

#### Outputs

*   **HTTP Response from `/research`**:
    *   `report` (string): The generated research report in Markdown format.
    *   `sources` (list of strings): A list of URLs or identifiers for the sources used.
    *   `costs` (dictionary): Contains `total_cost` (float) and `total_tokens` (integer).
    *   `num_sources` (integer): The total number of research sources found.

#### Environment Variables

*   **`OPENAI_API_KEY`**: Required for the GPTResearcher to function, enabling interaction with the OpenAI API for report generation and research processing.
*   **`TAVILY_API_KEY`**: Required for the GPTResearcher to function, likely used for search and information retrieval through the Tavily API.

#### User Interface

The agent includes a simple web-based user interface accessible at the root endpoint (`/`). This interface allows users to input research queries and view the generated reports directly in their browser.