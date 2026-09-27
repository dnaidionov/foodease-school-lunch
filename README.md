# Foodease School Lunch

A reusable skill that helps a parent choose and submit school meal orders on [Foodease](https://app.foodease.cafe/), using the child’s menu and the family’s preferences.

It orders for the whole month unless you give specific dates. If a preferred meal is unavailable, it chooses the day’s default unless that conflicts with a hard restriction. It submits meal orders, but **does not add funds or make payments**. You handle any required payment yourself.

## Install the skill

### Easiest: ask your assistant

If your assistant can install skills from GitHub, give it this link and ask:

> Install the Foodease School Lunch skill from this GitHub repository: https://github.com/dnaidionov/foodease-school-lunch. The `SKILL.md` file is in the repository’s main folder.

If it can’t install the skill directly, ask it to guide you through uploading the skill ZIP in that assistant’s settings.

### ChatGPT

If your ChatGPT account has **Skills**:

1. Open **Skills** and choose **Create → Upload from your computer**.
2. Choose a ZIP of this skill folder. You can get one from GitHub by selecting **Code → Download ZIP** on this repository page.
3. Follow the prompts to install it. In a work or school account, an administrator may need to allow skill uploads.

### Claude

1. Download the ZIP from this repository using **Code → Download ZIP**.
2. In Claude, open **Customize → Skills → + Create skill → Upload a skill**.
3. Choose the downloaded ZIP and turn the skill on.
4. If Claude asks, enable **Code execution and file creation** in **Settings → Capabilities**. Work or school accounts may be managed by an administrator.

## Use it

The assistant needs browser control to interact with Foodease. Allow it to use the Foodease website when prompted. Sign in directly on the website; never send your password in the chat. If the assistant can’t control a browser, it may be able to help review choices, but it can’t place the order.

Start with a request like:

> Use the Foodease School Lunch skill to order lunch for next month. I’ll sign in when prompted. Ask me for any meal preferences you need, then remember them for future orders. Submit the meal orders, but don’t add funds or make a payment. Show me the order when you’re done.

For a specific period, say:

> Use the Foodease School Lunch skill to order lunch for October 5–16. Use the preferences I’ve already given you. I’ll sign in when prompted. Submit the meal orders, but don’t add funds or make a payment. Show me the order when you’re done.

The first time, the assistant may ask which child and meals to order, foods they like or avoid, whether to include optional items, and what to choose when a preferred meal isn’t available. It is designed to reuse those preferences later when it can access the saved family profile. If it can’t find the profile, it should ask rather than guess.

After submitting, the assistant should show the dates, meals, and total. Review the order in Foodease and handle any funding or payment yourself.

## Important

- Each parent uses their own Foodease account and signs in themselves.
- The skill never adds money, enables auto-pay, or makes a payment.
- The menu, prices, and website can change. The assistant should check them each time.
- Don’t put family preferences, account details, or passwords in this shared repository.
