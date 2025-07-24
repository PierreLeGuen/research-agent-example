**Name**: Research Agent

**Description**: A web-based agent powered by GPT Researcher that conducts comprehensive research and generates detailed reports on various topics. It leverages large language models and search capabilities to gather information and synthesize findings, providing a structured report along with source attribution and cost estimates.

**Functionality**:
*   **Conducts Research**: Takes a user-defined query and performs in-depth research across multiple online sources.
*   **Generates Reports**: Produces various types of reports, including comprehensive research reports, resource reports, or outline reports, based on the user's selection.
*   **Provides Source Information**: Lists the URLs of the sources used during the research process.
*   **Estimates Costs**: Offers an estimation of the cost incurred for the research.
*   **Web Interface**: Provides a simple web-based user interface for submitting research requests and displaying results.

**Inputs**:
*   **Web Interface (HTTP POST to `/research`)**:
    *   **Query** (string): The specific topic or question to be researched (e.g., "Latest developments in AI ethics").
    *   **Report Type** (string, optional, default: "research_report"): The desired format of the output report. Supported types include "research_report", "resource_report", and "outline_report".

**Outputs**:
*   **Web Interface (HTTP Response from `/research`)**:
    *   **Report** (string): The generated research report content.
    *   **Sources** (list of strings): A list of URLs of the web pages used as sources.
    *   **Costs** (dictionary): Contains `total_cost` (numeric) and `total_tokens` (numeric, though often 0 as token count isn't directly provided by GPT Researcher).
    *   **Num Sources** (integer): The total number of unique sources identified.
*   **Web Interface (HTTP GET from `/`)**: An interactive HTML page allowing users to input queries and view results.

**Environment Variables**:
*   `OPENAI_API_KEY`: Your OpenAI API key, essential for the GPTResearcher library to interact with OpenAI's models for report generation and synthesis.
*   `TAVILY_API_KEY`: Your Tavily API key, required by GPTResearcher for efficient search and information retrieval from the web.