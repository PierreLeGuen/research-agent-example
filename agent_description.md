### Research Agent

This agent is a web-based research assistant powered by GPT Researcher. It conducts comprehensive research on a given query and generates detailed reports, summarizing information from various sources. It also provides a list of the sources used and calculates the associated costs.

**Main Functions:**
*   **Conduct Research:** Takes a research query and a specified report type (e.g., research, resource, outline) to gather information from the web.
*   **Generate Reports:** Produces a structured report based on the gathered research, including a summary and relevant details.
*   **Source Attribution:** Provides a list of URLs from which information was retrieved.
*   **Cost Estimation:** Reports the estimated cost of the research process.

**Inputs:**
*   **HTTP POST to `/research`**:
    *   `query` (string): The research topic or question.
    *   `report_type` (string, optional): The type of report to generate (e.g., "research_report", "resource_report", "outline_report"). Defaults to "research_report".

**Outputs:**
*   **HTTP JSON Response from `/research`**:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs for the sources used in the research.
    *   `costs` (dictionary): Contains `total_cost` (float) and `total_tokens` (integer, currently 0 as not directly provided by GPT Researcher).
    *   `num_sources` (integer): The total number of research sources found.

**Environment Variables:**
*   **`OPENAI_API_KEY`**: Required for interacting with OpenAI models, which are used by GPT Researcher.
*   **`TAVILY_API_KEY`**: Required for using the Tavily search API, essential for information retrieval.