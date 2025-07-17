# Research Agent

## Summary
The Research Agent is a web-based tool powered by GPT Researcher that conducts comprehensive research and generates detailed reports based on a given query. It provides various report types, including research, resource, and outline reports, along with information on sources and estimated costs.

## Main Functions
*   **Conduct Research**: Takes a user-defined query and a specified report type (e.g., research, resource, or outline report) to perform in-depth research.
*   **Generate Reports**: Produces well-structured reports based on the conducted research, summarizing findings and providing relevant information.
*   **Provide Sources and Costs**: Returns a list of source URLs used in the research and an estimate of the total cost incurred for the research process.
*   **Web Interface**: Offers a user-friendly web interface for submitting research queries and viewing results directly in the browser.
*   **Health Check**: Provides an endpoint to check the operational status of the agent and verify API key configurations.

## Inputs
*   **HTTP (Web Interface)**:
    *   **Query**: A text string representing the topic to be researched.
    *   **Report Type**: A selection from available report types (e.g., "research_report", "resource_report", "outline_report").

## Outputs
*   **HTTP (JSON)**:
    *   **Report**: The generated research report content.
    *   **Sources**: A list of URLs from which information was gathered.
    *   **Costs**: A dictionary detailing the total cost of the research.
    *   **Num Sources**: The total number of sources utilized.
*   **HTTP (HTML)**:
    *   A dynamic web page displaying the research input form and the formatted research results.

## Environment Variables
*   **`OPENAI_API_KEY`**: Your API key for accessing OpenAI services, essential for the GPTResearcher's language model capabilities.
*   **`TAVILY_API_KEY`**: Your API key for accessing Tavily search services, used for information retrieval and searching.