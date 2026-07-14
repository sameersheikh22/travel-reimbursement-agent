# Travel Reimbursement Approval Agent

**AI Developer Candidate Assignment — Sameer Shaik**

The single deliverable is the notebook: **[`sameershaik.ipynb`](sameershaik.ipynb)** — it contains the full README (setup, environment variables, how to run), the agentic pipeline, the audit trail, the results dashboard, the Design Notes & Reasoning, and the final structured JSON results for all five sample claims.

## Quick start

```bash
git clone https://github.com/sameersheikh22/travel-reimbursement-agent.git
cd travel-reimbursement-agent
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

# auth — either a free Gemini API key…
export GOOGLE_API_KEY=<your key>          # aistudio.google.com
# …or Vertex AI application-default credentials
gcloud auth application-default login
export GOOGLE_CLOUD_PROJECT=<your project>

jupyter notebook sameershaik.ipynb        # Run ▸ Run All Cells
```

No credentials? The notebook still runs end-to-end using its deterministic rules-engine fallback.

## At a glance

- **Agent:** Gemini 2.5 Flash (Vertex AI) driving 7 deterministic tools through an explicit function-calling loop.
- **Tools:** policy lookup, item eligibility, receipt completeness, per-diem limits, timeliness, duplicate detection, approval thresholds.
- **Reliability:** schema-enforced JSON output with a decision enum, output validator with retry, amount reconciliation, deterministic cross-check (disagreement ⇒ Manual Review), offline fallback.
- **Dashboard:** rendered in-notebook and saved as [`UI SS_1.png`](UI%20SS_1.png) / [`UI SS_2.png`](UI%20SS_2.png), plus an interactive ipywidgets form to edit and re-evaluate claims.
