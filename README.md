RunRate — Markets & Cricket Prediction Assistant
RunRate is a dual-mode AI chatbot that combines stock market signal analysis with cricket match prediction in a single conversational interface. Built as a portfolio project to demonstrate applied data science and full-stack thinking, it lets users switch between two domains — Markets and Cricket — each backed by its own lightweight analytical engine, with a Claude-powered chat layer on top for natural-language follow-up.
Features
Markets mode
Enter a stock ticker and timeframe (intraday / swing / position)
Generates a technical signal using RSI, moving-average trend, momentum, and a volatility proxy
Classifies the result into Buy / Sell / Hold zones
Cricket mode
Enter two teams' recent form (e.g. WWLWW) and venue
Computes a win-probability split using a weighted statistical model factoring in recent results and home-ground advantage
Conversational layer
Every tool output feeds directly into the chat context
The Claude API explains the numbers in natural language — English or Hinglish — instead of leaving the user to interpret raw stats
Mirrors how a real analyst assistant would work: run the numbers, then talk through what they mean
Tech Stack
HTML, CSS, JavaScript (single-file, no build step)
Anthropic Claude API (claude-sonnet-4-6) for conversational reasoning
Custom JS-based technical and statistical models (no external ML libraries)
How It Works
The current build uses a deterministic synthetic-data model — results are seeded from the input (ticker name, team names) so they stay consistent across runs rather than being random. This keeps the project fast, dependency-free, and fully client-side, while still demonstrating the analytical logic that would sit behind a production version.
Known Limitation
The chat feature calls the Anthropic API directly from the frontend without a backend proxy or API key management. This works inside the Claude.ai artifact environment but will not work if deployed standalone (e.g. on GitHub Pages) without adding a backend to securely handle the API key. The Markets and Cricket calculator tools work independently of this and function fully standalone.
Planned Extensions
Replace synthetic data with live sources: yfinance for market data, a cricket stats API for real fixtures and player stats
Add a FastAPI backend to handle the Claude API key securely and enable full deployment
Persist chat history and past predictions per user
Disclaimer
This project is built for educational and portfolio purposes only.
Nothing in this app is financial advice — market outcomes are inherently uncertain and no model here should be used for real trading decisions.
Nothing in this app facilitates or encourages real-money betting — cricket predictions are for informational and fan-interest purposes only.
Author
Akhil Mishra — BCA (Data Science & AI), Shri Ramswaroop Memorial University, Lucknow
GitHub: akhilmishra11
