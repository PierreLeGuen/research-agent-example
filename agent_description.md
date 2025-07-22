### Research Agent

The Research Agent is a web-based application designed to conduct comprehensive research and generate detailed reports based on user queries. It utilizes the GPT Researcher library to gather information from multiple sources, process it, and present a structured report. Users can specify the research topic and the desired report format.

#### Inputs

*   **Web Interface (HTTP POST to `/research`)**:
    *   `query` (string): The specific topic or question for which research is to be conducted.
    *   `report_type` (string, optional): The desired type of report to be generated. Supported types include "research_report" (default), "resource_report", and "outline_report".

#### Outputs

*   **Web Interface (HTTP GET from `/`)**: Serves an interactive HTML page allowing users to submit research queries and view the results directly in their browser.
*   **Web Interface (HTTP POST response from `/research`)**: A JSON object containing the research results:
    *   `report` (string): The comprehensive research report content, formatted in Markdown.
    *   `sources` (list of strings): A list of URLs from the external sources used during the research.
    *   `costs` (dictionary): Information about the estimated cost of the research, including `total_cost` and `total_tokens`.
    *   `num_sources` (integer): The total count of unique sources utilized in the research.

#### Environment Variables

*   **`OPENAI_API_KEY`**: An API key from OpenAI, essential for the agent to interact with OpenAI's language models for report generation.
*   **`TAVILY_API_KEY`**: An API key from Tavily, required for the agent to perform web searches and retrieve up-to-date information.