# Governance Trading Agent

An automated trading system that monitors cryptocurrency governance proposals, analyzes their sentiment, and executes trades based on the predicted market impact.

## Documentation

Available documentation in `docs/`:

- [Environment Setup Guide](docs/env_setup.md) - Configure environment variables, API keys, and trading parameters
- [Data Adapters Guide](docs/data_adapters.md) - Set up Firebase/MongoDB/custom data sources
- [Trade Flow Documentation](docs/trade_flow.md) - Trading workflow and sentiment analysis
- [API Endpoints Documentation](docs/api_endpoints.md) - REST API reference and examples

For new users, follow the guides in the order listed above.

# Quick Setup Guide

This guide provides a simplified step-by-step process to set up and run the Governance Trading Agent.

## Step 1: Install Ollama and Pull Mistral 7B Model

1. Download and install Ollama from [Ollama's official website](https://ollama.com/download)
2. Pull the Mistral 7B model:
   ```bash
   ollama pull mistral:7b
   ```
3. Verify the installation:
   ```bash
   ollama list
   ```


## Step 2: Clone Repository and Install Dependencies

1. Clone the repository in a virtual env:
   ```bash
   python -m venv venv
   source venv/bin/activate
   git clone https://github.com/agent-thor/governance-trading-agent.git
   cd governance_trade
   mkdir data
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure `coin.json` and `precision.json` are in the exchange directory


## Step 3: Download Trading Models

Run the download script to automatically download and set up the models:

```bash
python download_models.py
```

This script will:
- Create the necessary model directories
- Download the models from Google Drive
- Extract them to the correct locations
- Verify the installation

## Step 4: Configure Environment Variables

1. Copy the example environment file:
   ```bash
   cp .env.example .env
   ```

2. Edit the `.env` file with your actual credentials. For detailed information about required and optional environment variables, see the [Environment Variables Setup Guide](docs/env_setup.md).

## Step 5: Run the Agent

Start the agent using one of the following methods:

```bash
# Method 1: Using the Python module (recommended)
python -m main

# Method 2: Direct script execution
python main.py
``` 

If you face any problem, follow [data adapter guide](docs/data_adapters.md).


## Conclusion

The Governance Trading Agent provides an automated solution for monitoring cryptocurrency governance proposals and executing trades based on sentiment analysis. By following this documentation, you should be able to:

1. Install and configure the agent with your preferred settings
2. Run the agent to monitor proposals and execute trades
3. Use the API to manage trades manually when needed
4. Customize the data provider to fetch proposals from different sources

For additional support or to report issues, please visit the [GitHub repository](https://github.com/agent-thor/Governance-Trading-Agent/tree/main) or join our [Discord community](https://discord.gg/mbCe4jBuYW).

Happy trading!