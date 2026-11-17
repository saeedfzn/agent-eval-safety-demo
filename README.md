# Enterprise AI agents: orchestration, injection defences and evals (concept demo)

**Live demo:** https://saeedfzn.github.io/agent-eval-safety-demo/

A one-page, clickable concept showing how I'd design, secure and evaluate a multi-agent assistant for a fictional organisation (Larkspur Group). Built for a Forward Deployed Engineer (AI Agents) application.

- **Architecture:** an orchestrator with no data access, routing to four specialists (HR policy, IT helpdesk, document search, mail). Select an agent to see its tools (MCP, REST, Graph), grounding source, identity and what it can't do.
- **Run console:** eight requests, each traced step by step: routing, tool calls and the identity they ran under, citations, the answer. Side-effecting actions pause on an approval card (a mock, not a Microsoft UI).
- **Prompt injection:** a planted document and a planted email try to get data out. Five defence layers (untrusted-content tagging, user permissions, tool allow-lists, human approval, an egress filter); switch four of them off and watch the outcome change, including a "model is fooled anyway" worst case. No layer prevents injection on its own; each lowers the odds or limits the damage.
- **Evaluation suite:** ten tests (grounding, hallucination, routing, permission boundary, refusal, injection, approval) computed by running the same simulator, with a release gate. One quality test is scripted to fail, to show a grounding gap.
- **Identity and permissions:** acting on behalf of the user versus as the app, per agent. Design only.
- **Build notes:** how I'd implement it on Microsoft Foundry, plus a deployment and handover checklist. Design only.

**Honest scope:** every run is simulated and deterministic; no LLM is called. The organisation, people, documents and figures are made up. I haven't used Microsoft Foundry, Azure OpenAI, Azure AI Search, Semantic Kernel, Agent Framework or Teams apps in production. The Adaptive Card payload is an untested sketch.

Plain HTML, CSS and JavaScript in one file, no dependencies. Light and dark mode, works on a phone.

Built by Faizaan Saeed · [LinkedIn](https://www.linkedin.com/in/faizaan-saeed-ba96a426b) · [Portfolio](https://saeedfzn.github.io/)

Microsoft, Microsoft Foundry, Azure, Entra, Microsoft Graph, Teams, Outlook and SharePoint are trademarks of the Microsoft group of companies; Claude is a trademark of Anthropic. Independent demo, not affiliated with or endorsed by Microsoft.
