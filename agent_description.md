### Research Agent

The Research Agent is a web-based tool powered by GPT Researcher that conducts comprehensive research and generates detailed reports on specified topics. It provides a user-friendly interface to submit research queries and view the generated reports, including sources and estimated costs.

#### Functionality
- **Conducts Research**: Takes a user query and performs in-depth research using the GPT Researcher library.
- **Generates Reports**: Produces various types of reports, including:
    - **Research Report**: A comprehensive analysis of the query.
    - **Resource Report**: A collection of relevant resources.
    - **Outline Report**: A structured outline of the research topic.
- **Provides Sources**: Lists the URLs of the sources used to compile the report.
- **Estimates Costs**: Displays the estimated cost of the research.
- **Web Interface**: Offers a simple web application for submitting queries and displaying results.

#### Inputs
- **Medium**: HTTP POST request
- **Endpoint**: `/research`
- **Format**: JSON
- **Parameters**:
    - `query` (string, required): The specific topic or question for research.
    - `report_type` (string, optional): The desired type of report. Defaults to "research_report". Supported types include "research_report", "resource_report", and "outline_report".

#### Outputs
- **Medium**: HTTP JSON response
- **Endpoint**: `/research`
- **Format**: JSON
- **Parameters**:
    - `report` (string): The generated research report content.
    - `sources` (list of strings): A list of URLs from which information was gathered.
    - `costs` (dictionary): Contains `total_cost` (float) and `total_tokens` (integer) related to the research.
    - `num_sources` (integer): The total count of unique sources identified.

#### Environment Variables
- `OPENAI_API_KEY`: Required for authenticating with the OpenAI API, which is essential for the GPTResearcher's operation.
- `TAVILY_API_KEY`: Required for authenticating with the Tavily API, used for search and information retrieval by the GPTResearcher.