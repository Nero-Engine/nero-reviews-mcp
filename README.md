# Nero Reviews

Verified job reviews for tradespeople (electricians, plumbers, builders, any trade), collected by the trade's own AI assistant.

After every job the assistant calls `job_done` and gets a one-time link to text the customer. The customer taps 1 to 5 stars on their phone, in the trade's own colours and logo, and can add a sentence. The trade can ask "what's my score?" and hear a short spoken answer. Every trade gets a public page with their score, level and reviews, newest first.

**Endpoint:** `https://nero-reviews.nerolabs.workers.dev/mcp` (MCP, Streamable HTTP, no sign-in)
**Sample trade page (made-up business):** https://nero-reviews.nerolabs.workers.dev/t/brightwire-electrical-sample
**How to connect:** https://nero-reviews.nerolabs.workers.dev/docs
**Privacy:** https://nero-reviews.nerolabs.workers.dev/privacy
**Support:** founder@neroengine.com
**Try it:** the sample key `nrk_sample_brightwire_test_mode_only` works on the made-up business.

Test mode: free, nothing is charged, and Nero never contacts anyone. The trade or their assistant sends the link.

## Tools

| Tool | What it does |
|---|---|
| `register_trade` | Sets up a business once (name, colours, logo, optional Google review link). Returns the trade key and the public page. |
| `update_trade` | Changes the details shown on the pages. |
| `job_done` | Call after every finished job. Returns a one-time review link, a neutral message to send, and WhatsApp and text links. |
| `my_score` | Score, level, jobs to the next level, low reviews waiting for a reply, and a `spoken` answer to read aloud. |
| `list_reviews` | Every review, newest first (the only order). |
| `reply_to_review` | The trade's one public reply. Checked for retaliation: no surnames, contact details, insults, threats or talk of money owed. |
| `dispute_review` | The dispute desk. Settles a dispute about a review straight away from fixed rules and returns the verdict, why, and an example reply. |
| `export_history` | The full record, ready to carry into Nero Work. |
| `review_rules` | The review law rules this server enforces, in plain words. |

Every tool carries a plain title and the read-only, destructive and open-world hints.

## Fair by design (UK DMCC Act 2024 and CMA fake review guidance)

1. Every customer is asked, never only the happy ones.
2. Nothing is ever offered for a review.
3. Reviews are never edited, hidden or sorted by stars. The database refuses edits and deletes.
4. Every review is marked as coming from a verified job.
5. The optional Google review button is the same for 1 star and 5 stars.
6. The trade can reply once and give their side, but cannot hit back.
7. If the job is put right, only the customer can add an update. The original stays visible.

Phone numbers, emails, addresses, swearing and hate words are removed from reviews by machine, before publishing and again every time a review is shown. The stars always count.

Anyone can report a review that breaks the law with the Report link under it; personal details and abuse are checked by machine on the spot, and legal problems go to a short queue Nero reads every morning. A customer can remove their own name and words from their own link; their stars stay, unnamed, so no business can push them into deleting a rating. Pages: [how reviews work](https://nero-reviews.nerolabs.workers.dev/how-reviews-work), [privacy](https://nero-reviews.nerolabs.workers.dev/privacy).

## Connect

- **Claude Code:** `claude mcp add --transport http nero-reviews https://nero-reviews.nerolabs.workers.dev/mcp`
- **Claude (desktop or web):** Settings, Connectors, Add custom connector, paste the endpoint.
- **ChatGPT:** Settings, Apps and Connectors, Create (developer mode), paste the endpoint.
- **Cursor and others:**

```json
{ "mcpServers": { "nero-reviews": { "url": "https://nero-reviews.nerolabs.workers.dev/mcp" } } }
```

Then say "set me up on Nero Reviews".

## Example

`my_score` on the made-up sample business returns, among other fields:

```
"spoken": "Brightwire Electrical. Your score is 4.3 out of 5 from 6 reviews. You have 8 verified jobs, so you are New. 2 more jobs until Level 5. 2 customers have not left stars yet. Newest review: 5 stars from Mrs P., ..."
```

Built by Nero Labs. Not legal advice.
