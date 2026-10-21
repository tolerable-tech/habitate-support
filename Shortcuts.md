---
title: Shortcuts & Automations
description: Ready-made Siri and Shortcuts recipes for Habitate, including checking in automatically when you close another app.
permalink: /shortcuts/
---

# Habitate Shortcuts & Automations

Habitate works with **Siri** and the **Shortcuts** app, so you can check in to a goal without opening Habitate. You can even check in automatically right after you finish something in another app.

This page has ready-to-use recipes and step-by-step setup instructions.


---

**Enjoying Habitate?** A quick [rating or review on the App Store](https://apps.apple.com/app/id6783581150?action=write-review) helps other people find it.

---

## Contents

- [The Habitate actions](#the-habitate-actions)
- [Recipe: Log a language-learning streak (e.g. Duolingo) when you close the app](#recipe-log-a-language-learning-streak-eg-duolingo-when-you-close-the-app)
- [Recipe: Your own Siri phrase](#recipe-your-own-siri-phrase)
- [Recipe: Any other app](#recipe-any-other-app)
- [Troubleshooting](#troubleshooting)

---

## The Habitate actions

Open the **Shortcuts** app, add an action, and search for **Habitate** to find these:

| Action | What it does |
|--------|--------------|
| **Check In** | Marks a goal as done for today. For goals that track an amount (pages, minutes, glasses…) you can fill in **Amount**. Running it again on a goal that's already done does nothing, so it never un-checks a goal. |
| **Is Goal Done Today?** | Returns **true** if the goal is already checked in today and **false** if it isn't. Use it with **If** to skip a step once you're done for the day. |

Siri also understands these phrases out of the box. Use your goal's name in them:

- "Log **Meditate** in Habitate"
- "Mark **Meditate** done in Habitate"
- "Is **Meditate** done in Habitate?"

---

## Recipe: Log a language-learning streak (e.g. Duolingo) when you close the app

**What it does:** When you close your language app, Habitate asks *"Did you finish today's lesson?"* Tap **Yes** and your goal is checked in. Once the goal is done for the day it stops asking.

Pick whichever way suits your iPhone:

- **[Option A: Describe it to Shortcuts](#option-a-describe-it-to-shortcuts)**: one step, on the latest iOS.
- **[Option B: Install the ready-made shortcut](#option-b-install-the-ready-made-shortcut)**, then add the automation.
- **[Option C: Build it yourself](#option-c-build-it-yourself)**, then add the automation. For older iOS versions or devices without Apple Intelligence.

### Option A: Describe it to Shortcuts

On the latest iOS, Shortcuts can build the whole thing, including running it when you close the app, from a plain description. Open **Shortcuts**, tap **+**, describe what you want, and paste something like this:

```
When I close Duolingo, check whether my "Duolingo" goal is done today in Habitate. If it isn't, ask me "Did you finish today's lesson?" with the options Yes and Not yet. If I pick Yes, check in my "Duolingo" goal in Habitate.
```

Replace the goal name in quotes with the **exact name of your goal** in Habitate. If your language app isn't Duolingo, change the first part too.

**Check what it built.** It should use Habitate's **Is Goal Done Today?** and **Check In** actions, both set to your goal, and look roughly like the outline in [option C](#option-c-build-it-yourself). If something's off, tell it what to change or edit the actions directly. That's it, you're done.

### Option B: Install the ready-made shortcut

1. On your iPhone, open this link: **[Get the "Log Lesson in Habitate" shortcut](TODO-ICLOUD-LINK)**
2. Tap **Add Shortcut**.
3. If it asks you to pick a goal, choose the Habitate goal you use for your lessons. If it doesn't ask, open the shortcut in the Shortcuts app and tap the **Goal** field in **both** Habitate actions to choose your goal.

> A shared shortcut can't know your goals, so this step is required. Until it's done, the shortcut will ask "Which goal?" every time it runs.

Then [add the automation](#add-the-automation-options-b-and-c).

### Option C: Build it yourself

<details markdown="1">
<summary>Show step-by-step instructions</summary>

1. Open **Shortcuts**, tap **+**, and name the new shortcut **Log Lesson in Habitate**.
2. Add **Is Goal Done Today?** (search "Habitate") and tap **Goal** to pick your goal.
3. Add **If**. Set it to: *Is Goal Done Today?* **is** **false**.
4. Inside the **If**, add **Choose from Menu**:
   - Prompt: `Did you finish today's lesson?`
   - Options: `Yes` and `Not yet`
5. Under **Yes**, add **Check In** and pick the **same goal**.
6. Leave **Not yet** empty.

</details>

When you're done it should look like this:

```
Is [Your Goal] done today?
If  Is Goal Done Today  is  false
    Choose from Menu "Did you finish today's lesson?"
        Yes      →  Check in [Your Goal]
        Not yet  →  (nothing)
    End Menu
End If
```

Then add the automation below.

### Add the automation (options B and C)

Automations live only on your device and can't be shared, so if you installed or built the shortcut, set this part up yourself:

1. In **Shortcuts**, go to the **Automation** tab and tap **+** (or **New Automation**).
2. Choose **App**.
3. Tap **Choose** and select your language app (for example, Duolingo).
4. Select **Is Closed** and deselect **Is Opened**.
5. Select **Run Immediately** so it doesn't ask for permission every time. You can also turn off **Notify When Run**.
6. Tap **Next**, then choose the **Log Lesson in Habitate** shortcut.

That's it. The next time you leave the app you'll be asked once, and once you've checked in it stays quiet until tomorrow.

> **Tip:** "Is Closed" fires whenever you leave the app, including switching to another app partway through a lesson. If that happens, just tap **Not yet**.

---

## Recipe: Your own Siri phrase

Siri's built-in phrases have to include "Habitate". To use a phrase of your own, like *"I meditated"*:

1. Open **Shortcuts** and tap **+**.
2. Add **Check In** (search "Habitate") and pick your goal.
3. Name the shortcut exactly what you want to say, e.g. **I meditated**.

Now say *"Hey Siri, I meditated"* and the goal is checked in.

On the latest iOS you can also just describe it in Shortcuts: *"Check in my Meditate goal in Habitate. Name the shortcut 'I meditated'."*

---

## Recipe: Any other app

The [language-learning recipe](#recipe-log-a-language-learning-streak-eg-duolingo-when-you-close-the-app) works with **any** app. Just swap in a different app, question, and goal, either in your description or in the shortcut and automation. For example:

- Close a **meditation app** → "Did you meditate today?" → check in *Meditate*
- Close a **workout app** → "Did you finish your workout?" → check in *Exercise*
- Close a **reading app** → "Did you read today?" → check in *Read*

---

## Troubleshooting

**My goal doesn't appear when I tap "Goal".**
Open Habitate once so the Shortcuts app picks up your latest goals. Archived goals aren't listed.

**It says "I couldn't find that goal in Habitate."**
The goal the shortcut points to was deleted. Open the shortcut and pick the goal again in each Habitate action.

**It asks "How much?" or "How many…?"**
That goal tracks an amount. Fill in **Amount** on the **Check In** action (tap the arrow next to it to show the field). You can also put **Ask for Input** in front of it to type the amount each time.

**The automation asks before running.**
Edit the automation and choose **Run Immediately**.

**Still stuck?** [Open a support request](README.md#open-a-support-request) and we'll help.

---

**Enjoying Habitate?** A quick [rating or review on the App Store](https://apps.apple.com/app/id6783581150?action=write-review) helps other people find it.

---

<sub>Duolingo is a trademark of Duolingo, Inc. Habitate is not affiliated with, endorsed by, or sponsored by Duolingo or any other app mentioned here. App names are used only to describe how Habitate can be used alongside them.</sub>
