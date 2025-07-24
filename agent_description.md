### Research Agent

The Research Agent is an AI-powered service designed to conduct comprehensive research and generate detailed reports based on user-provided queries. It leverages the GPT Researcher library to gather information from various sources and synthesize it into structured, informative reports.

#### Functionality

*   **Comprehensive Research**: Performs in-depth research on a given topic, collecting information from multiple online sources.
*   **Report Generation**: Generates different types of reports, including general research reports, resource reports, and outline reports, based on the user's specified type.
*   **Source Attribution**: Provides a list of URLs for the sources used in the research, enhancing transparency and verifiability.
*   **Cost Estimation**: Offers an estimate of the operational costs associated with conducting the research.

#### Inputs

*   **HTTP POST Request to `/research`**
    *   `query` (string, required): The specific topic or question to be researched.
    *   `report_type` (string, optional, default: "research_report"): The desired format of the output report. Options include "research_report", "resource_report", and "outline_report".

#### Outputs

*   **HTTP JSON Response from `/research`**
    *   `report` (string): The generated research report content.
    *   `sources` (list of strings): A list of URLs of the sources utilized during the research.
    *   `costs` (dictionary): Contains cost-related information, including `total_cost`.
    *   `num_sources` (integer): The total count of unique research sources found.

#### Requirements

*   **OPENAI_API_KEY**: An API key for OpenAI services, which is essential for the agent's AI-powered research capabilities.
*   **TAVILY_API_KEY**: An API key for Tavily, used for efficient search and information retrieval during the research process.