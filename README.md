<p align="center"><img src="logo.png" alt="PersonaXpand" width="240"></p>

# PersonaXpand MCP server

Run your own social media accounts from Claude and other AI assistants. Post, schedule, answer comments and DMs in your own voice, and check your analytics across 8 social networks.

- **Endpoint:** `https://personaxpand.com/mcp` (remote, Streamable HTTP)
- **Auth:** OAuth 2.0 with dynamic client registration and PKCE. No API key to copy.
- **Official MCP Registry:** `com.personaxpand/personaxpand`
- **Docs:** https://personaxpand.com/features/ai-assistants
- **Guide:** [How to manage your social media with Claude](https://personaxpand.com/blog/how-to-manage-social-media-with-claude)

This is a hosted server. This repository holds its description and registry entry, not its source code.

## What you can do

**Posting and scheduling.** Write a post in chat, then publish it now, schedule it, or let PersonaXpand pick your best time. One post can go to Instagram, Facebook, X, LinkedIn, YouTube, Threads, Pinterest and Bluesky, each version checked against that network's rules first. Pause, move or delete scheduled posts.

**Replies to comments, DMs and mentions.** See what came in, read a conversation and answer it. The assistant shows you each reply and sends it only after you say yes. Approve or turn down reply drafts, and change your auto-reply settings and rules. Replies work on Instagram, Facebook, X, YouTube and Threads; DMs on Instagram and Facebook.

**Analytics.** A summary of how your posts did, a fresh pull from the networks, and your best times to post.

**Media.** Add a photo or video from a link, or from a one-time upload link.

## Setup

You need a PersonaXpand account (https://personaxpand.com) with at least one social network connected inside it.

**Claude:** add a custom connector and paste `https://personaxpand.com/mcp` as the URL. PersonaXpand is also listed in Claude's connector directory. A sign-in window opens; sign in to PersonaXpand and choose **Read only** or **Read and act**.

**Other MCP clients:** any client that supports remote MCP servers with OAuth can connect to the same URL.

## Example prompts

- "Which social media accounts do I have connected?"
- "Write a short post saying we're open 10am to 6pm this weekend and schedule it for LinkedIn and Bluesky tomorrow at 9am."
- "What comments and messages came in today? Which ones are questions?"
- "Draft replies to the questions and show them to me before sending."
- "How did my posts do over the last 30 days, and when should I post next week?"
- "Pause everything scheduled for Friday."

## Tools

| Area | Tools |
|---|---|
| Account | `get_profile`, `list_connected_accounts`, `get_plan_usage`, `get_voice`, `get_notifications` |
| Posts | `create_post`, `update_post`, `get_post`, `list_posts`, `schedule_post`, `reschedule_post`, `publish_post_now`, `pause_post`, `resume_post`, `delete_post` |
| Inbox and replies | `list_inbox`, `get_conversation`, `send_reply`, `schedule_reply`, `mark_handled`, `list_reply_drafts`, `approve_reply_draft`, `reject_reply_draft` |
| Auto-replies | `get_auto_reply_settings`, `set_auto_reply`, `set_account_auto_reply`, `create_auto_reply_rule`, `update_auto_reply_rule`, `delete_auto_reply_rule` |
| Analytics | `get_analytics_summary`, `refresh_analytics`, `get_best_times` |
| Media | `list_media`, `import_media_from_link`, `create_upload_link`, `get_upload_result` |

Read tools are marked read-only. Tools that post, reply, edit or delete are marked destructive, so your assistant asks before running them.

## Safety

- It only ever works on your own account, within your plan's limits.
- Every change made through an assistant is listed in PersonaXpand under Account Settings, Connected apps, where you can remove the connection at any time.
- Messages other people send you reach the assistant marked as outside text, never as instructions.
- Captions and replies follow your own writing voice from My Twin.
- Privacy: https://personaxpand.com/privacy-policy#s8a

## Support

info@personaxpand.com · https://personaxpand.com

PersonaXpand is made by Nextoria Information Technology LLC.
