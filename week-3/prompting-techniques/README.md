# Prompting Techniques: Support-Desk Assistant

The four scripts use Ollama with `llama3.1:8b`. Install Ollama, start its service, and
pull that model before running the checks:

```powershell
ollama pull llama3.1:8b
python -m pip install -r requirements.txt
python k_shot_prompting.py
python chain_of_thought.py
python tool_calling.py
python rag.py
```

Each script prints its PASS/FAIL results. The checks were run with Ollama and
`llama3.1:8b`; the observed results are in `writeup.md`. The tool-calling starter check
verifies the model's function call and then prints the local fixture result; it does not
ask the model for a second, post-tool response.
