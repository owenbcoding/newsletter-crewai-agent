# AI Newsletter Workflow Documentation

## Overview

This multi-agent system uses three specialized AI agents to automatically generate professional AI newsletters. The workflow follows a sequential process where each agent builds upon the work of the previous one.

## Workflow Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                        INPUT                                 │
│                   Topic: "Artificial Intelligence"           │
│                   Current Year: 2025                         │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                    AGENT 1: RESEARCHER                       │
│            AI News & Research Intelligence Specialist       │
├─────────────────────────────────────────────────────────────┤
│  Task: Research Task                                        │
│  ─────────────────────────────────────────────────────────  │
│  • Find 3 most significant AI news items                    │
│  • Identify 1 top AI research paper                         │
│  • Gather details, context, and significance                │
│                                                              │
│  Output:                                                     │
│  • Structured research brief with all findings              │
│  • Headlines, key details, sources                          │
│  • Paper title, authors, findings, significance             │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                     AGENT 2: EDITOR                          │
│           AI Newsletter Editor & Content Strategist         │
├─────────────────────────────────────────────────────────────┤
│  Task: Drafting Task                                        │
│  ─────────────────────────────────────────────────────────  │
│  • Create Section 1: 3-bullet news roundup                  │
│  • Create Section 2: 3 detailed paragraphs                  │
│  • Create Section 3: 1 research spotlight paragraph         │
│  • Maintain professional, engaging tone                     │
│                                                              │
│  Output:                                                     │
│  • Complete newsletter draft in markdown                    │
│  • Three clearly defined sections                           │
│  • Polished, engaging content ready for review              │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                    AGENT 3: REVIEWER                         │
│        AI Newsletter Quality Assurance Specialist           │
├─────────────────────────────────────────────────────────────┤
│  Task: Review Task                                          │
│  ─────────────────────────────────────────────────────────  │
│  • Verify content accuracy and quality                      │
│  • Check structure and formatting                           │
│  • Ensure grammatical perfection                            │
│  • Make final improvements and corrections                  │
│                                                              │
│  Output:                                                     │
│  • Final, publication-ready newsletter                      │
│  • Saved to: newsletter.md                                  │
│  • Impeccably formatted and polished                        │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                    FINAL OUTPUT                              │
│                   newsletter.md                              │
│  ───────────────────────────────────────────────────────── │
│  Section 1: AI News Roundup (3 bullets)                    │
│  Section 2: Deep Dive (3 paragraphs)                       │
│  Section 3: Research Spotlight (1 paragraph)               │
└─────────────────────────────────────────────────────────────┘
```

## Agent Details

### 1. Researcher Agent
**Role:** AI News & Research Intelligence Specialist

**Capabilities:**
- Discovers trending AI news and developments
- Identifies significant research papers
- Evaluates importance and relevance
- Gathers comprehensive details and context

**Goal:** Discover and curate the most significant and recent developments in AI, including breaking news and cutting-edge research papers

### 2. Editor Agent
**Role:** AI Newsletter Editor & Content Strategist

**Capabilities:**
- Transforms research into engaging prose
- Structures content for maximum impact
- Maintains professional technical tone
- Ensures clarity and accessibility

**Goal:** Transform research findings into engaging, well-structured newsletter content that is clear, concise, and compelling for a technical audience

### 3. Reviewer Agent
**Role:** AI Newsletter Quality Assurance Specialist

**Capabilities:**
- Ensures factual accuracy
- Checks formatting consistency
- Verifies grammatical precision
- Polishes content to professional standards

**Goal:** Ensure the newsletter meets the highest standards of accuracy, clarity, formatting, and professional quality before publication

## Output Format

The final newsletter follows this exact structure:

### Section 1: AI News Roundup
A concise overview with 3 bullet points (1-2 sentences each) highlighting the most important AI developments.

**Purpose:** Quick overview for busy readers

**Format:**
```markdown
- **Headline 1** - Brief description of the development and why it matters
- **Headline 2** - Brief description of the development and why it matters
- **Headline 3** - Brief description of the development and why it matters
```

### Section 2: Deep Dive
Three detailed paragraphs (4-6 sentences each) that expand on each news item from Section 1.

**Purpose:** Provide context, technical details, and implications

**Format:** Three standalone paragraphs, each focusing on one news item in depth

### Section 3: Research Spotlight
One comprehensive paragraph (5-7 sentences) featuring the most significant AI research paper.

**Purpose:** Highlight cutting-edge research and its impact on the field

**Format:** A single, well-crafted paragraph introducing the paper, explaining its contribution, and discussing its significance

## Usage

### Basic Usage

```bash
# Navigate to project directory
cd /home/owencodes/Projects/newsletter_crew

# Run the crew
crewai run
```

### Customizing the Topic

Edit `src/newsletter_crew/main.py`:

```python
inputs = {
    'topic': 'Your Custom Topic',  # e.g., "Computer Vision", "NLP", "Robotics"
    'current_year': str(datetime.now().year)
}
```

### Modifying Agent Behavior

1. **Agents**: Edit `src/newsletter_crew/config/agents.yaml` to change roles, goals, or backstories
2. **Tasks**: Edit `src/newsletter_crew/config/tasks.yaml` to modify task descriptions or expected outputs
3. **Workflow**: Edit `src/newsletter_crew/crew.py` to add tools, change process flow, or adjust configurations

## Configuration Files

### agents.yaml
Defines the three agents with their roles, goals, and backstories.

### tasks.yaml
Defines the three tasks (research, drafting, review) with detailed descriptions and expected outputs.

### crew.py
Orchestrates the agents and tasks, defines the sequential workflow.

### main.py
Entry point for running the crew, contains input parameters.

## Best Practices

1. **API Keys**: Always set up your OpenAI API key in `.env` before running
2. **Topic Specificity**: More specific topics yield more targeted newsletters
3. **Iteration**: Run multiple times to see variations in output quality
4. **Customization**: Adjust agent backstories to change writing style and tone
5. **Tools**: Consider adding web search or document retrieval tools for more accurate research

## Troubleshooting

### Issue: No output file generated
**Solution**: Check that your OpenAI API key is correctly set in `.env`

### Issue: Generic or vague content
**Solution**: Make the topic more specific in `main.py`

### Issue: Output format doesn't match specification
**Solution**: Review and adjust task descriptions in `tasks.yaml`

### Issue: Slow execution
**Solution**: This is normal for multi-agent workflows. Each agent needs time to process and generate content.

## Example Output

See `newsletter_example.md` for a complete example of what the final newsletter looks like.

## Future Enhancements

Potential improvements to consider:

1. **Web Search Integration**: Add real-time web search tools to the Researcher agent
2. **Email Integration**: Automatically send the newsletter via email
3. **Scheduling**: Set up automated daily/weekly newsletter generation
4. **Custom Sources**: Add RSS feeds or specific websites for targeted research
5. **Image Generation**: Include relevant images or infographics
6. **Analytics**: Track which topics and formats perform best

## Credits

Built with [CrewAI](https://crewai.com) - A powerful framework for orchestrating autonomous AI agents.

