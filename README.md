# SynthPanel

SynthPanel is a Streamlit prototype for AI-assisted synthetic customer interviews. Analysts select a data-grounded customer cluster, ask a product or research question, and receive a persona-specific response with a confidence indicator.

It is a demonstration tool for financial-services market research, not a production decisioning system.

## Features

- Persona-led interviews derived from clustering outputs.
- Azure OpenAI-powered responses scoped to the selected persona.
- Data-backed, inference, and extrapolation confidence signals.
- Processed data artifacts and standalone interactive cluster visualizations.

## Run locally

Requires Python 3.10+ and an Azure OpenAI resource with compatible deployments.

```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/synthpanel-project.git
cd synthpanel-project
python -m venv .venv
pip install -r requirements.txt
```

Copy `.env.example` to `.env`, replace the placeholder values, then run:

```bash
streamlit run app.py
```

Required configuration:

```env
AZURE_OPENAI_ENDPOINT=https://YOUR-RESOURCE.openai.azure.com/
AZURE_OPENAI_API_KEY=your-secret-key
AZURE_OPENAI_DEPLOYMENT=your-chat-deployment
```

`AZURE_OPENAI_API_VERSION` and the `*_NANO` variables in `.env.example` are optional.

## Repository contents

- `app.py` — Streamlit application and Azure OpenAI integration.
- `cluster_profiles.json` — persona profiles loaded by the app.
- `data/` — approved processed datasets, persona outputs, and clustering artifacts.
- `synthpanel_heatmap*.html` — standalone visualization exports.
- `assets/` — project diagram and imagery.

## Data and security

Only approved processed/derived artifacts are included. Original input files and internal supporting documentation are excluded. Verify authorization, privacy, and governance requirements before reusing included data. Never commit `.env`, Azure credentials, or session-export JSON files.

## License

Released under the [MIT License](LICENSE).
