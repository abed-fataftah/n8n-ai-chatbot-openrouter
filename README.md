# AI Chatbot with n8n and OpenRouter

An AI chatbot built with n8n, using a Chat Trigger, AI Agent, and OpenRouter Chat Model.

## How it works

1. A user sends a message through the n8n chat interface.
2. The Chat Trigger passes the message to the AI Agent.
3. The agent uses the connected OpenRouter model to generate a reply.

## Setup

1. Download [`workflow.json`](./workflow.json).
2. In n8n, open a workflow and select **Import → From file** from the workflow menu.
3. Import `workflow.json`.
4. Open **OpenRouter Chat Model** and create or select an OpenRouter credential using your own API key.
5. Choose an available model. The export is configured with `nvidia/nemotron-3.5-lightning:free`; availability and provider limits can change.
6. Click **Open chat** and send a message, such as: `Explain automation in one sentence.`

## Included nodes

| Node | Purpose |
| --- | --- |
| When chat message received | Starts the workflow when a chat message arrives |
| AI Agent | Processes the message using the connected model |
| OpenRouter Chat Model | Provides the language model through OpenRouter |

## Notes

- No conversation memory or tools are connected in this version.
- The workflow is exported as inactive; importing it does not publish a live chatbot.
- API keys, credential references, and instance metadata are excluded. Configure your own credentials in n8n.
- If a request is rate limited, retry later or select another available model.

## Validation

The exported JSON was checked for valid structure and node connections. The cleaned export has not been executed in a separate n8n instance.
