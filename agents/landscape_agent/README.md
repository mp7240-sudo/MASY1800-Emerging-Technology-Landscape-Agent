# Emerging Technology Landscape Agent

MASY1-GC 1800 Assignment 8 | 0.2-student | November 10, 2026

The agent compares alternatives and identifies which evidence could change a fictional regional bank’s six-month decision about LLM-assisted wealth-management intake. It uses the frozen common intake and JSON response schema.

- [Landscape comparison, tests and team handoff](records/agent_record.md)
- [Dated original-source evidence register](records/evidence_register.md)
- [Validator results](records/validation_results.txt)
- [Completed Word Agent Record](records/Assignment_8_Landscape_Agent_Record.docx)

## Reproduce the tests

From the repository root, use Python 3 to check the frozen core and generate both prompt packets.

```sh
python3 tools/check_frozen_core.py
python3 tools/build_prompt.py --agent agents/landscape_agent --case agents/landscape_agent/cases/primary.json
python3 tools/build_prompt.py --agent agents/landscape_agent --case agents/landscape_agent/cases/contrast_1.json
```

Send each packet in a separate ChatGPT conversation. Save each response as JSON and run `python3 tools/validate_response.py <response-file>`. For the controlled comparison, use the same evidence in both cases. For a new decision date, refresh the register from original sources and update both cases together.

The actual model outputs are in [responses](responses/). The first contrast is preserved as incomplete text. [v0.1](records/v0.1/) includes the initial instructions, metadata and packets. [v0.2](records/v0.2/) holds the revised packets. Raw model outputs are test artifacts. The recorded judgment and limitations are in the Agent Record.
