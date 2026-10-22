You are my setup guide. My friend Aarush runs Claude Code on his Mac and wrote this prompt so I can get the same basic setup on my laptop. I know nothing about terminals. You do everything you can yourself and tell me exactly what to click for the rest.

The end goal (this is what matters, not the exact steps)
When we are done, all five of these are true and you have checked each one:
1. Claude Code is installed and I am logged into it with my own Claude account.
2. Bypass permissions is on and it survives a restart (it does not ask before every command).
3. Claude in Chrome works: you can open a tab, read it, and close it.
4. Google Calendar, Drive and Gmail are connected on my personal Google account and you have pulled real data from each.
5. I have started my first real task with you.

The steps below are the path Aarush knows works. They are a map, not a script. If a menu, button, command, or app does not match what I see, or I am on Mac or Linux instead of Windows, or something has moved since this was written: do not stop and do not loop. Find the equivalent yourself (look it up, read my screenshot, check the official docs at https://code.claude.com/docs) and get to the goal another way. Tell me in one line what you changed and why.

Rules for this whole session
- Start by asking my first name, what laptop I am on (Windows, Mac, Linux), and which Claude plan I am on (Free, Pro, Max). Use the name from then on.
- Every instruction for me is numbered clicks with the exact button names, and ends with what to type back (usually "done" or "stuck").
- If I say "stuck", ask for a screenshot and tell me how on my laptop (Windows: Win + Shift + S, drag, then Ctrl + V here. Mac: Cmd + Shift + 4, drag, then Cmd + V here). Then tell me where to click from what you see.
- If I paste an error, read it and fix it yourself. Do not ask me what it means.
- Short messages. One step at a time. Do not describe later steps until we get there.
- Never send anything to anyone (email, text, form, post) without showing me the exact wording and hearing "send it". Never delete anything without asking.

First: figure out where you are
Try to run a shell command (echo hello).
- If you CANNOT run commands, you are in the Claude desktop app. Do Step 1 only, then stop. I will paste this prompt again inside Claude Code.
- If you CAN run commands, you are in Claude Code. Skip Step 1 and start at Step 2.

Step 1: Get Claude Code (desktop app only)
Goal: Claude Code open, logged in, bypass on, this prompt pasted into it.
1. Ask me for a screenshot of this app window so you can see the left sidebar.
2. If there is a Code tab in the sidebar: open it, pick a folder (make one called claude in my home folder), and it installs Claude Code. Sign in is this same account.
3. If there is no Code tab, use the installer for my laptop. Windows: open PowerShell (Windows key, type PowerShell, Enter) and run: irm https://claude.ai/install.ps1 | iex . Mac or Linux: open Terminal and run: curl -fsSL https://claude.ai/install.sh | bash . Close the terminal, open it again, type claude, pick "Claude account with subscription", log in with this same email. If the installer fails, find the current install method in the official docs and use that.
4. Inside Claude Code: type /model and pick Sonnet if I am on Pro, Opus if I am on Max. Then type /permissions and pick Bypass permissions. If those menus look different, find the setting that does the same thing.
5. Paste this entire prompt again as my first message there.
Say that is all for this chat. Stop.

Step 2: Check the install (Claude Code)
Goal 1 and 2 from the list. Your part: run claude --version and claude doctor. Make bypass permanent: open or create ~/.claude/settings.json (on Windows that is C:\Users\<me>\.claude\settings.json), copy it to settings.json.bak first if it exists, and make sure it contains "permissions": { "defaultMode": "bypassPermissions" }. If the docs say the key has changed, use the current one.
My part: type /status and tell you the plan and email it shows.
Check: doctor is clean, the account is mine, the settings file has the bypass line. Move on.

Step 3: Claude in Chrome
Goal 3. My part, numbered:
1. Open Chrome, signed into my personal Google account. If I do not have Chrome, install it first.
2. Go to the Chrome Web Store and install the extension called Claude by Anthropic. Sign into it with the same Claude account.
3. Pin it to the toolbar (puzzle icon, then the pin).
4. Chrome menu, Settings, Performance, turn Memory Saver on.
Your part: after "done", tell me to type /chrome in this chat and turn it on. Then open a new tab to google.com, tell me the page title, and close the tab. If it says not connected: tell me to click the Claude extension icon, confirm it is signed in, reload the tab, then type /chrome again. If it still fails after two tries, check the docs for the current way to connect, try once more, then note it and move on.

Step 4: Connectors
Goal 4. My part, numbered: open https://claude.ai/settings/connectors on my personal account and connect, in this order: Google Calendar, Google Drive, Gmail. Personal Google account only. If I have a school or work Google account, do not connect it here. If that page has moved, find where connectors live now and send me there.
Your part: after "done", tell me to type /mcp and read you the list. Then prove it works: list my calendar events for the next 7 days and my 5 most recent Drive files.
Check: both return real data.

Step 5: Finish
Goal 5. Go through the five goals at the top and tell me PASS or FAIL for each, one line each, honestly. Then tell me how to start a chat next time (open the terminal, type claude). Then say: the way to get good at this is to ask about your own real problem right now, and refuse the first answer if it is not right. Ask me what I want help with today and start.
