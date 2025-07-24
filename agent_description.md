### Research Agent

The Research Agent is a web-based service powered by GPT Researcher that conducts comprehensive research and generates detailed reports based on user queries. It can produce various types of reports, including general research, resource lists, or outlines.

**Functionality:**
*   **Conducts Research:** Takes a user-defined query and leverages external APIs (OpenAI and Tavily) to gather information from multiple sources.
*   **Generates Reports:** Produces structured reports based on the gathered research, with options for different report types (e.g., research report, resource report, outline report).
*   **Provides Sources and Costs:** Returns the URLs of the sources used for research and an estimate of the total cost incurred during the research process.
*   **Web Interface:** Offers a simple web interface for users to submit queries and view results directly in their browser.

**Inputs:**
*   **HTTP POST Request to `/research`**:
    *   `query` (string): The topic or question to research.
    *   `report_type` (string, optional): The desired type of report (e.g., "research_report", "resource_report", "outline_report"). Defaults to "research_report".

**Outputs:**
*   **HTTP JSON Response from `/research`**:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs from which information was retrieved.
    *   `costs` (dictionary): Contains information about the research cost, including `total_cost` and `total_tokens`.
    *   `num_sources` (integer): The total number of sources identified.
*   **HTTP HTML Content from `/`**: A user interface to interact with the agent.

**Environment Variables:**
*   `OPENAI_API_KEY`: Your API key for accessing OpenAI services, essential for the agent's research and report generation capabilities.
*   `TAVILY_API_KEY`: Your API key for Tavily, used for search and information retrieval during the research process.