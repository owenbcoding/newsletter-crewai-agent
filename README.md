# Trip Planner Crew

Welcome to the Trip Planner Crew project, powered by [crewAI](https://crewai.com). This multi-agent system automatically generates detailed travel itineraries by orchestrating three specialized agents: a Researcher, a Planner, and a Reviewer. The agents collaborate to research real-time travel information, create detailed hour-by-hour itineraries with specific costs and times, and ensure publication-quality output.

## Installation

Ensure you have Python >=3.10 <3.14 installed on your system. This project uses [UV](https://docs.astral.sh/uv/) for dependency management and package handling, offering a seamless setup and execution experience.

First, if you haven't already, install uv:

```bash
pip install uv
```

Next, navigate to your project directory and install the dependencies:

(Optional) Lock the dependencies and install them by using the CLI command:
```bash
crewai install
```
## Configuration

Before running the project, you need to set up your API key:

1. Create a `.env` file in the project root:
   ```bash
   touch .env
   ```

2. Add your API keys to the `.env` file:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   SERPER_API_KEY=your_serper_api_key_here
   ```
   
   Note: You need a Serper API key for web searches. Get one free at [https://serper.dev](https://serper.dev)

### Customizing

The workflow is already configured to generate detailed trip itineraries. However, you can customize:

- **Trip Parameters**: Modify the inputs in `src/newsletter_crew/main.py`:
  - `destination`: Your travel destination (e.g., "Paris, France", "Tokyo, Japan")
  - `duration`: Number of days for the trip
  - `budget`: Budget amount
  - `currency`: Currency code (USD, EUR, GBP, etc.)
- **Agents**: Modify `src/newsletter_crew/config/agents.yaml` to adjust agent roles and backstories
- **Tasks**: Modify `src/newsletter_crew/config/tasks.yaml` to change task descriptions and output formats
- **Tools**: Add custom tools in `src/newsletter_crew/tools/` and integrate them into agents in `src/newsletter_crew/crew.py`

## Running the Project

To kickstart your crew of AI agents and begin task execution, run this from the root folder of your project:

```bash
$ crewai run
```

This command initializes the Trip Planner Crew, assembling the agents and assigning them tasks as defined in your configuration.

This will execute the multi-agent workflow and generate an `itinerary.md` file with your detailed travel itinerary in the root folder.

## Understanding Your Crew

The Trip Planner Crew is composed of three specialized AI agents working in sequence:

### Agents

1. **Researcher** - Travel Research & Intelligence Specialist
   - Uses web search tools to find real-time travel information
   - Gathers current prices, opening hours, and booking details
   - Finds authentic reviews and insider tips

2. **Planner** - Expert Trip Itinerary Planner
   - Creates detailed, hour-by-hour itineraries
   - Includes specific times, durations, costs, and tips
   - Ensures activities are well-paced and logistically feasible

3. **Reviewer** - Travel Itinerary Quality Assurance Specialist
   - Ensures all details are present (times, costs, durations, tips)
   - Verifies schedule feasibility and budget compliance
   - Produces publication-ready final output

### Workflow

The workflow follows a sequential process:

1. **Research Task**: The Researcher searches the web for current travel information (attractions, restaurants, costs, hours)
2. **Planning Task**: The Planner creates a detailed day-by-day itinerary with specific times and costs
3. **Review Task**: The Reviewer ensures quality, format consistency, and completeness

### Output Format

The final itinerary includes detailed daily schedules:

**Each Day Includes:**
- **Specific Times**: "Morning (9:00 AM - 12:00 PM)"
- **Activity Details**: Clear description of what to do
- **Duration**: "Duration: 2 hours"
- **Costs**: "Cost: €25 (adult ticket)"
- **Tips**: "Tip: Pre-book tickets online to avoid queues"

**Example:**
```markdown
## Day 1: Iconic Paris

**Morning (9:00 AM - 12:00 PM):** Visit the Eiffel Tower

Duration: 2 hours

Cost: €25 (adult ticket)

Tip: Pre-book tickets online to avoid long queues.
```

### Customization

You can customize your trip by modifying the inputs in `src/newsletter_crew/main.py`:

```python
inputs = {
    'destination': 'Paris, France',    # Your travel destination
    'duration': '7',                   # Number of days
    'budget': '2000',                  # Budget amount
    'currency': 'USD'                  # Currency (USD, EUR, GBP, etc.)
}
```

## Features

✅ **Real-Time Web Research**: Uses Serper to search for current prices, hours, and booking info  
✅ **Detailed Time Blocks**: Every activity has specific start and end times  
✅ **Actual Costs**: Real prices pulled from web searches, not estimates  
✅ **Practical Tips**: Insider advice for each activity  
✅ **Budget-Conscious**: Stays within your specified budget  
✅ **Actionable Output**: Ready-to-use itineraries with all the details you need  

## Support

For support, questions, or feedback regarding the Trip Planner Crew or crewAI:
- Visit our [documentation](https://docs.crewai.com)
- Reach out to us through our [GitHub repository](https://github.com/joaomdmoura/crewai)
- [Join our Discord](https://discord.com/invite/X4JWnZnxPb)
- [Chat with our docs](https://chatg.pt/DWjSBZn)

Let's create amazing travel experiences together with the power and simplicity of crewAI!
