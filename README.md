# Claude BlockRun Skill

A skill for using BlockRun to access external AI models and services through a wallet-based, usage-priced workflow. It covers model calls, real-time X search, image generation, wallet setup, and spending controls.

## What It Covers

- **External model access:** Route requests to supported model providers, including OpenAI, xAI, Google, and DeepSeek.
- **Real-time X search:** Use Grok with Live Search for current X/Twitter data.
- **Image generation:** Generate images through supported image models.
- **Second opinions:** Delegate reviews or reasoning tasks to another model.
- **Wallet and balance:** Initialize the BlockRun wallet, inspect the address, and check the USDC balance.
- **Budget controls:** Track spending and stop making calls when a user-defined budget is reached.
- **Cost awareness:** Review model and search pricing before executing paid requests.

## Installation

Clone the repository into your Claude skills directory:

```bash
git clone https://github.com/Brajesh31/claude-blockrun-skill.git ~/.claude/skills/blockrun
```

Install the SDK:

```bash
python -m pip install blockrun-llm
```

## Using the Skill

Example requests:

```text
Use BlockRun to ask GPT for a second opinion on this architecture.
```

```text
Use Grok with Live Search to check recent posts about this topic on X.
```

```text
Use BlockRun to generate an image from this prompt and report the cost.
```

The skill instructs Claude to use BlockRun when explicitly requested or when an external capability is needed. It also distinguishes cases where Claude can handle the task without invoking a paid external service.

## Wallet and Spending

The SDK setup flow can initialize a wallet and expose balance and spending information. Fund and use the wallet only after understanding the network, payment flow, and costs. Set a clear budget for paid operations and verify spending after calls.

## Repository Resources

- [SKILL.md](SKILL.md) contains setup instructions, examples, available model identifiers, pricing references, and troubleshooting guidance.

## Security and Cost Notes

Never expose wallet secrets or session files. Review the active pricing before making calls because model availability and prices can change. Use explicit spending limits for multi-call workflows, and obtain user authorization before any paid operation unless the user has already clearly authorized it.
