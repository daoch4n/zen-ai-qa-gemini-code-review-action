# 👁️‍🗨️ code-review-action 👀
<img src="https://github.com/user-attachments/assets/7e1493ad-31da-448d-8050-e2072c916500" alt="cute transparent robot" width="256">

## Reviews your Pushes to main branch and Pull Requests for 🆓 using latest Gemini Flash 2.5 5/20 Preview with previous feedback reevaluation on update ✨

### Usage:
- Put `.py` and `.yml` files in `.github/workflows/` folder of your repo
- Go to [AI Studio](https://aistudio.google.com/apikey) and obtain Gemini API key there
- From repo page on Github go to `Settings` -> `Secrets and variables` -> `Actions`
  - Click `New repository secret`
    - Name: `GEMINI_API_KEY`
    - Secret: the API key you just got from [AI Studio](https://aistudio.google.com/apikey) in JSON format: [ key ]
- It will automatically run on pushes to main branch and pull request creation , update and reopen
- For pushes to main branch, detailed review feedback since last push will be auto-commited to your repo `/reviews/` folder (separate from PR feedback)
- For Pull Requests, detailed review feedback will be commented on completion with `Resolve conversation` button <br> along with AI-actionable JSON report (in two formats) <br> auto-commited by cute white robot to your repo `/reviews/` folder (separate from main branch commits feedback)
### (Optional) <br> If you also want it to comment as cute white robot:
- Make you own app in Developer settings and use its installation ID and key! 🗝️
- From repo page on Github go to `Settings` -> `Secrets and variables` -> `Actions`
  - Click `New repository secret`
    - Set `ZEN_APP_INSTALLATION_ID` with the installation ID <br> (you can find installation ID in url of app settings page (the one that displays after you install app, not the one you generate private key on))
    - Set `ZEN_APP_PRIVATE_KEY` with your app private key generated in [app settings](https://github.com/settings/apps/)

Inspired by [truongnh1992/gemini-ai-code-reviewer](https://github.com/truongnh1992/gemini-ai-code-reviewer)
<br><br>
Differences:
- Talks to you as cute white robot <br> (if you set it up)
- Automatically runs on PR creation, update , reopen
- Batches hunks related to same files <br> to optimize rate limiting
- Makes use of Gemini 1 million tokens context window <br> by attaching whole file together with changes for better context
- Optimized diff parsing algoritm <br> that works better with GitHub (maybe?)
- Uses Structured Output mode of Gemini API <br> for better parsing of AI output
- Auto-commits AI-actionable JSON report <br> as cute white robot to your repo `/reviews/` folder <br> for futher agentic processing
- Uses JSON file in question during next run <br> to load previous comments from last run <br> for better context
- Loads API key from Github Actions secrets in JSON format: [ key ]
- Compliance with Provider Terms: Users of qa-gemini-action are solely responsible for ensuring that their use of this tool complies with the terms of service, usage policies, and any other relevant agreements of the AI service providers
