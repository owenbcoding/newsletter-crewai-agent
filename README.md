# AI Newsletter Crew

Welcome to the AI Newsletter Crew project, powered by [crewAI](https://crewai.com). This multi-agent system automatically generates professional AI newsletters by orchestrating three specialized agents: a Researcher, an Editor, and a Reviewer. The agents collaborate to research the latest AI developments, draft engaging content, and polish the final newsletter to publication quality.

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

2. Add your OpenAI API key to the `.env` file:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   ```

### Customizing

The workflow is already configured to generate AI newsletters with the specified format. However, you can customize:

- **Topic**: Modify the `topic` parameter in `src/newsletter_crew/main.py` to focus on specific AI areas (e.g., "Machine Learning", "Computer Vision", "Natural Language Processing")
- **Agents**: Modify `src/newsletter_crew/config/agents.yaml` to adjust agent roles and backstories
- **Tasks**: Modify `src/newsletter_crew/config/tasks.yaml` to change task descriptions and output formats
- **Tools**: Add custom tools in `src/newsletter_crew/tools/` and integrate them into agents in `src/newsletter_crew/crew.py`

## Running the Project

To kickstart your crew of AI agents and begin task execution, run this from the root folder of your project:

```bash
$ crewai run
```

This command initializes the newsletter-crew Crew, assembling the agents and assigning them tasks as defined in your configuration.

This will execute the multi-agent workflow and generate a `newsletter.md` file with the final newsletter in the root folder.

## Understanding Your Crew

The AI Newsletter Crew is composed of three specialized AI agents working in sequence:

### Agents

1. **Researcher** - AI News & Research Intelligence Specialist
   - Discovers the latest AI news stories and research papers
   - Curates 3 significant news items and 1 featured research paper
   - Evaluates the significance and relevance of developments

2. **Editor** - AI Newsletter Editor & Content Strategist
   - Transforms research into engaging newsletter content
   - Drafts structured sections with appropriate detail levels
   - Maintains professional tone for a technical audience

3. **Reviewer** - AI Newsletter Quality Assurance Specialist
   - Ensures accuracy, clarity, and professional quality
   - Checks formatting consistency and grammar
   - Produces publication-ready final output

### Workflow

The workflow follows a sequential process:

1. **Research Task**: The Researcher finds the 3 most significant AI news items and 1 top research paper
2. **Drafting Task**: The Editor creates a structured newsletter with three sections
3. **Review Task**: The Reviewer polishes and finalizes the newsletter

### Output Format

The final newsletter includes three sections:

**Section 1: AI News Roundup**
- 3 concise bullet points highlighting key developments

**Section 2: Deep Dive**
- 3 detailed paragraphs expanding on each news item

**Section 3: Research Spotlight**
- 1 comprehensive paragraph featuring a significant AI research paper

### Customization

You can customize the newsletter by modifying the `topic` parameter in `src/newsletter_crew/main.py`:

```python
inputs = {
    'topic': 'Artificial Intelligence',  # Change this to focus on specific AI topics
    'current_year': str(datetime.now().year)
}
```

## Support

For support, questions, or feedback regarding the NewsletterCrew Crew or crewAI.
- Visit our [documentation](https://docs.crewai.com)
- Reach out to us through our [GitHub repository](https://github.com/joaomdmoura/crewai)
- [Join our Discord](https://discord.com/invite/X4JWnZnxPb)
- [Chat with our docs](https://chatg.pt/DWjSBZn)

Let's create wonders together with the power and simplicity of crewAI.
