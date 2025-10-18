# Quick Start Guide

Get your AI Newsletter Crew up and running in 5 minutes!

## Prerequisites

- Python 3.10 or higher
- OpenAI API key

## Setup Steps

### 1. Install Dependencies

```bash
cd /home/owencodes/Projects/newsletter_crew
pip install uv
crewai install
```

### 2. Configure API Key

Create a `.env` file in the project root:

```bash
echo "OPENAI_API_KEY=your_actual_api_key_here" > .env
```

Replace `your_actual_api_key_here` with your OpenAI API key.

### 3. Run the Workflow

```bash
crewai run
```

That's it! The multi-agent system will:
1. Research the latest AI news and papers
2. Draft a structured newsletter
3. Review and polish the final output
4. Save the result to `newsletter.md`

## Expected Output

The workflow will generate a `newsletter.md` file with:

- **Section 1**: 3-bullet point news roundup
- **Section 2**: 3 detailed paragraphs expanding on each news item
- **Section 3**: 1 paragraph highlighting a featured AI research paper

## Customization

### Change the Topic

Edit `src/newsletter_crew/main.py`:

```python
inputs = {
    'topic': 'Machine Learning',  # Change this to your preferred AI topic
    'current_year': str(datetime.now().year)
}
```

### Examples of Topics
- "Artificial Intelligence" (default - broad coverage)
- "Large Language Models" (focus on LLMs)
- "Computer Vision" (focus on CV research)
- "Robotics and AI" (focus on robotics)
- "AI Ethics and Safety" (focus on responsible AI)

## Viewing Results

```bash
cat newsletter.md
```

Or open `newsletter.md` in your favorite text editor.

## Example Output

Check out `newsletter_example.md` to see what a completed newsletter looks like.

## What Happens During Execution?

You'll see verbose output showing:

1. **Researcher Agent** searching for AI news and papers
2. **Editor Agent** drafting the newsletter content
3. **Reviewer Agent** polishing and finalizing

Each agent's thoughts and actions are logged for transparency.

## Typical Execution Time

- First run: ~3-5 minutes (depending on API response times)
- Subsequent runs: ~2-4 minutes

## Troubleshooting

### "No API key found"
**Fix**: Make sure your `.env` file exists and contains `OPENAI_API_KEY=...`

### "Module not found"
**Fix**: Run `crewai install` to install all dependencies

### "Empty output file"
**Fix**: Check the console logs for any errors during agent execution

## Next Steps

- Read `WORKFLOW.md` for detailed documentation
- Review `README.md` for configuration options
- Explore agent configurations in `src/newsletter_crew/config/`
- Customize agent behaviors and task descriptions

## Tips for Best Results

1. **Specific topics** generate more focused newsletters
2. **Run multiple times** to see different results
3. **Adjust agent backstories** in `agents.yaml` to change writing style
4. **Modify task descriptions** in `tasks.yaml` for different output formats

---

**Happy Newsletter Generation! 🚀**

