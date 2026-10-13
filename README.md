# How to Add a Claude Custom Connector for Video Generation (Step-by-Step, 2026)

Claude is great at writing scripts, storyboards and shot lists. Ask it to actually *make* the video, though, and it will politely tell you it can't. That's not a bug. Claude is a language model, and it has no built-in video generator.

The good news is that you don't have to leave Claude to get video. With a **custom connector**, you can plug a video tool straight into the chat, and Claude will drive it for you. This guide walks through what a custom connector is, how to add one for video generation, the first prompts to try, and how to fix the most common setup problems.

## What is a Claude custom connector?

A custom connector is a link between Claude and an outside service, built on the **Model Context Protocol (MCP)**. MCP is an open standard that lets an AI assistant call tools hosted somewhere else. The tool lives on its own server; Claude just needs its URL.

Once a connector is added, Claude can see the tools that server offers and call them when your request needs them. You still talk to Claude in plain English. The connector does the heavy lifting in the background and hands the results back to the chat.

That's the key idea: Claude becomes the director, and the connector is the crew.

## Why Claude has no built-in video

Video models are large, expensive to run, and change fast. In 2026 the strongest options come from different labs: Seedance, Kling, Veo, Gemini. No single chat assistant bundles all of them. Instead of waiting for Claude to ship one native video model, you connect a service that already gives you access to several, and pick whichever fits the shot.

## What you need

- **A Claude account.** Custom connectors work on the Free plan as well as paid plans. Free users can add one custom connector, which is enough for this setup.
- **A video tool that offers a remote MCP connector.** In this guide I use [Unsora](https://tryunsora.com), a creative toolkit for AI agents. One connector gives Claude access to Seedance 2.5, Kling 3, Veo 3.1 and Gemini Omni Flash, plus images, AI influencers, thumbnails, clipping and captions, 4K upscaling and post scheduling.
- **About two minutes.** There's nothing to install.

## Step 1: Open the connectors menu

In Claude, go to **Customize → Connectors**.

## Step 2: Add a custom connector

Click **+ Add → Add custom connector**. Claude asks for a name and a URL. Give it any name you like ("Unsora" works) and paste the MCP endpoint:

```
https://mcp.tryunsora.com/mcp
```

It's a remote MCP server, so there's nothing to install or configure locally.

## Step 3: Sign in

Claude opens a sign-in window for the service. Log in (or create an account), approve the connection, and you'll land back in Claude with the connector listed.

## Step 4: Turn it on in your chat

In a new chat, click the **+** button in the message box and make sure the connector is switched on. Claude only uses connectors that are enabled for that conversation.

That's the whole setup. If you also use Claude Code, Cursor, ChatGPT or another MCP client, the same URL works there too. Unsora's [setup instructions for each agent](https://tryunsora.com) cover the small differences.

## Your first video prompts

Start simple, then get specific. A few that work well:

> Make an 8-second cinematic shot of a coffee cup on a rainy windowsill, vertical 9:16.

> Generate the same scene with Kling 3 and Veo 3.1 so I can compare them.

> Create a 5-second slow push-in shot of a perfume bottle on marble for an Instagram ad.

Video jobs take a little while to render. Claude starts the job, waits for it, and shows you the result in the chat. If you don't like it, just say what to change: "warmer light", "slower camera", "make the cup red". You're the director giving notes, not someone learning a timeline.

A useful habit: ask Claude to write the prompt first. "Write three shot descriptions for a skincare ad, then generate the strongest one." Claude is good at prompt-writing, so let it.

## Troubleshooting the most common problems

**Claude says it can't make videos.** The connector probably isn't enabled in this chat. Click **+** in the message box and switch it on, then ask again.

**Claude won't let you add another connector.** On the Free plan you get one custom connector. Remove an old one under Customize → Connectors, or upgrade your Claude plan if you need several.

**The sign-in window closed or failed.** Remove the connector, add it again with the same URL, and complete the sign-in in one go. Pop-up blockers are a common culprit.

**The URL won't save.** Check that you pasted the full endpoint, including `https://` and the `/mcp` at the end.

**The video is taking a while.** Longer clips and higher-quality models take longer to render. Give it a minute before asking Claude to check on it.

## What a single connector adds beyond generation

Generating a clip is only half the job for a creator. The real time sink is everything after: cutting, captioning, resizing, uploading.

Because Unsora bundles those tools behind the same connector, Claude can carry a video all the way to publishing in one conversation:

- **Clip and caption.** Give it a long recording and ask for captioned 9:16 shorts. I wrote a full walkthrough of that workflow in [How to Turn One Long Video Into Captioned Shorts Using Claude](https://medium.com/@irfansadek/how-to-turn-one-long-video-into-captioned-shorts-using-claude-no-editing-skills-needed-3ec432694a2d).
- **Upscale.** Ask for a 4K version before you post.
- **Thumbnails.** Generate a thumbnail with your face for YouTube. There's a step-by-step in my [AI YouTube thumbnail guide](https://sites.google.com/view/ai-yt-thumbnail-guide).
- **Schedule.** Queue posts to TikTok, Instagram, YouTube, Facebook or LinkedIn from the same chat. Nothing goes out until you confirm.

If you're building a recurring character, the same connector handles AI influencers too. See [how to keep an AI influencer's face consistent across every video](https://aicreatorguidesbyunsora.wordpress.com/2026/10/13/how-to-keep-an-ai-influencers-face-consistent-across-every-video/).

## A full prompt you can copy

> Generate a 10-second vertical video of a barista pouring latte art in golden morning light using Seedance 2.5, upscale it to 4K, and schedule it to TikTok and Instagram for tomorrow at 9am.

Claude runs it in order: generate, wait, upscale, schedule. Your job is the idea and the final yes.

## Is it free?

Claude's custom connector feature is available on the free plan. Unsora is a paid service at $19, $39 or $149 a month, with a 3-day trial, so you can test the full setup before paying. (One note, since the names are close: Unsora is not OpenAI's Sora. It's a separate toolkit that gives your agent access to several video models.)

## The bottom line

Claude doesn't need built-in video to be a great video tool. Add one custom connector, paste one URL, sign in, and Claude can generate, refine, upscale and schedule video from a single chat. If you want to try the exact setup from this guide, [connect Unsora to Claude](https://tryunsora.com) and make your first clip today.
