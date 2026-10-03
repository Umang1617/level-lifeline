---
name: level-lifeline
description: Helps the user find the best guides and strategies for any game challenge. Opens Chrome to search for a web guide and AI Overview, then searches Reddit for community tips. Delivers a clean output with website name and link, a 3 line summary, and the top Reddit post title and link. Use when the user is stuck on a level, boss, team build, or any game challenge. Triggers on phrases like I am stuck, how do I beat, best strategy for, I keep losing, help me with this level, how to unlock, best team for, guide for.
argument-hint: "[game name] [problem]"
author: Umang Srivastava
version: 9
---

# Level Lifeline

## What This Skill Does
Searches for the best guide and community tips for any game challenge. Opens Chrome to find a web guide and reads the AI Overview summary, then searches Reddit for the top community post. Delivers a structured output with website name and link, a 3 line summary, and the Reddit post title and link.

## References
| Reference | When to load | What it covers |
|---|---|---|
| references/reddit-sources.md | Before Step 8 | Subreddits per game, how to pick the best Reddit post |
| references/output-template.md | Before Step 11 | Exact output format to follow |

---

## Steps

## Web Search Steps

### Step 1 - Get the details
Read **$0** (game name) and **$1** (problem or challenge).
If either is missing, ask one question: "Which game and what are you stuck on?"
Do not proceed until both are confirmed.

### Step 2 - Open Chrome
Open the Chrome browser inside BlueStacks.
Wait for Chrome to fully load before proceeding.

### Step 3 - Open a new tab
Once Chrome is open, open a new tab.
Wait for the new tab to fully load before proceeding.

### Step 4 - Search for the quest or guide
In the Chrome address bar or search bar, type:
`[game name] [problem] walkthrough guide`
Press Enter and wait for search results to load.

### Step 5 - Read the AI Overview
Before clicking any link, check if a Google AI Overview box appears at the top of the search results.
If AI Overview is present: read and extract the key strategy or tip shown in the AI Overview. This will be used in the 3 line summary.
If AI Overview is not present: skip this step and proceed to Step 6.

### Step 6 - Open the website
From the search results, click the most relevant link from a trusted game guide site or wiki.
Preferred sites in order: game-specific wiki (Fandom), gamepur.com, ign.com, gamesradar.com, pocket-tactics.com.
Wait for the page to fully load.

### Step 7 - Scroll to walkthrough section
Scroll down the page directly to the walkthrough, strategy, or guide section.
Look for headings like: Walkthrough, How to Beat, Strategy, Tips, Guide, Steps.
If no walkthrough section is found on this page, go back and try the next search result.
Extract:
- Website name
- Full page URL
- The core strategy from the guide (used to complete the 3 line summary alongside AI Overview)

---

## Reddit Search Steps

### Step 8 - Open Reddit
Load `references/reddit-sources.md`.
Open a new tab in Chrome and navigate to reddit.com inside BlueStacks.
Wait for Reddit to fully load before proceeding.

### Step 9 - Search for the quest on Reddit
In the Reddit search bar, type:
`[game name] [problem]`
Press Enter and wait for results to load.
Filter results by: Top or Hot to get the most relevant community posts.

### Step 10 - Select the best Reddit post
From the search results, pick the post that is:
- Most upvoted
- Has actual tips or answers in the comments (not just a question with no replies)
- From the game-specific subreddit if available (check references/reddit-sources.md)
Click and open the post.
Extract:
- Post title
- Full post URL
- Top upvoted comment or answer from the post (used in the 3 line summary)
If the post is NOT loading or returns an error: note this and skip the Reddit link in the output.

---

## Output Step

### Step 11 - Create the output
Load `references/output-template.md` now.
Follow the template exactly. Do not skip any section.
Combine findings from the web search (Steps 4-7) and Reddit search (Steps 8-10) to create the final output.

---

## STRICT RULES
- Do not skip any step. Follow each step in order.
- Do not proceed to the next step until the current step is complete.
- Never fabricate a website URL or Reddit link. Only use real URLs from visited pages.
- If Reddit post is not loading, share post title only with no link.
- If Chrome fails to open, retry once before reporting the issue to the user.

---

## Edge Cases
- If no relevant web guide is found after 3 search results: note this in output and proceed to Reddit only
- If no Reddit post is found: note this in output and provide the web guide only
- If both sources fail: tell the user honestly and suggest they search manually
- Never recommend cheats or anything against the game's terms of service
