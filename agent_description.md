**Name:** Research Agent

**Summary:** A research agent powered by GPT Researcher that conducts comprehensive research and generates reports based on a given query.

**Functionality:**
This agent provides an API to perform in-depth research on a given topic and generate detailed reports. It leverages the GPT Researcher library to gather information from various sources and synthesize it into structured reports. It also offers a user-friendly web interface for initiating research and viewing results directly in a browser.

**Inputs:**
*   **HTTP POST to `/research`**:
    *   `query` (string): The specific question or topic for which research is needed.
    *   `report_type` (string, optional): The desired format of the report. Options include "research_report" (default), "resource_report", or "outline_report".

**Outputs:**
*   **HTTP GET from `/`**: Serves an interactive web page (`index.html`) allowing users to input research queries and view results.
*   **HTTP POST from `/research`**: Returns a JSON object containing:
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs from the sources used in the research.
    *   `costs` (object): Details on the estimated cost of the research, including `total_cost`.
    *   `num_sources` (integer): The total number of distinct sources identified and used.
*   **HTTP GET from `/health`**: Returns a JSON object indicating the agent's operational status and whether required API keys are configured.

**Environment Variables:**
*   **`OPENAI_API_KEY`**: Required for accessing OpenAI services, which the GPT Researcher uses for language model capabilities.
*   **`TAVILY_API_KEY`**: Required for accessing Tavily search services, used by GPT Researcher for information retrieval and source gathering.