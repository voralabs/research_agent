# 🔍 AI Research Agent

Hey there! Welcome to my AI Research Assistant project - a smart little helper that digs through the web and Wikipedia to answer your questions. Built with LangGraph and LangChain, it's like having a super-powered research buddy at your fingertips.

## What's Cool About It?

- Searches multiple places at once:
  - Scours the web using Tavily
  - Dives into Wikipedia articles
- Uses GPT-4 to craft well-thought-out answers
- Built on LangGraph (because who doesn't love clean, organized code?)
- Comes with a neat visualization of how everything works

## Before You Start

You'll need:
- Python 3.7 or newer
- An OpenAI API key
- A Tavily API key (don't worry, it's free!)

## Getting Started

First, grab all the packages you need:
```bash
pip install -U langgraph tavily-python wikipedia langchain_openai langchain_community langgraph_sdk
```

## Setting Up Your Keys

Make sure you've got these environment variables ready to go:
- `OPENAI_API_KEY`: Get this from OpenAI
- `TAVILY_API_KEY`: Grab this from Tavily's website

## How It Does Its Magic

The assistant works in three simple steps:

1. **Gathering Info**:
   - Searches the web using Tavily
   - Pulls relevant stuff from Wikipedia
   
2. **Processing Everything**:
   - Takes all that info and organizes it nicely
   - Gets it ready for our AI friend to read

3. **Creating Answers**:
   - Uses GPT-4 to whip up helpful answers based on what it found

All of this is managed by LangGraph, which keeps everything running smoothly and efficiently.

## Want to Try It Out?

Here's how simple it is to use:
```python
# Get everything ready
graph = builder.compile()

# Ask away!
result = graph.invoke({"question": "What's on your mind?"})

# See what it found
answer = result['answer'].content
```

## Technical Bits

For the technically curious, here's how the state management works:
```python
class State(TypedDict):
    question: str
    answer: str
    context: Annotated[list, operator.add]
```

## Under the Hood

The system uses three main components:
- `search_web`: Your gateway to web results via Tavily
- `search_wikipedia`: Your Wikipedia explorer
- `generate_answer`: The piece that puts it all together

## Want to Help?

Found a bug? Have an idea to make it better? Jump right in! Issues and pull requests are always welcome.

---
**Pro tip**: Remember to keep those API keys secret when sharing your code!
