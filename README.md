<p align="left">
  <strong>TO DO LIST</strong><br />
  <em>A calm, Persian-first space for planning your day.</em>
</p>

<p align="left">
  <a href="https://nastaranmrz.github.io/today/"><img src="https://img.shields.io/badge/open-live%20app-7c3aed?style=flat-square" alt="Open the live app" /></a>
  <a href="https://github.com/Nastaranmrz/today"><img src="https://img.shields.io/github/stars/Nastaranmrz/today?style=flat-square&logo=github" alt="GitHub stars" /></a>
  <a href="https://github.com/Nastaranmrz/today/commits/main"><img src="https://img.shields.io/github/last-commit/Nastaranmrz/today?style=flat-square&logo=github&label=last%20update" alt="Last update on GitHub" /></a>
  <a href="TESTING.md"><img src="https://img.shields.io/badge/manual%20tests-documented-2f855a?style=flat-square" alt="Manual tests documented" /></a>
  <img src="https://img.shields.io/badge/interface-Persian%20%7C%20RTL-5b5870?style=flat-square" alt="Persian right-to-left interface" />
</p>

# To do list

Plan your day, keep track of what matters, and see your progress at a glance. To do list is a lightweight, right-to-left task planner designed around a Persian interface.

<p align="left">
  <a href="https://nastaranmrz.github.io/today/"><strong>→ Open the app</strong></a>
  &nbsp; · &nbsp;
  <a href="TESTING.md">Manual test guide (Persian)</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/Nastaranmrz/today/issues">Report an issue</a>
</p>

## What you can do

| | Feature | Details |
|---|---|---|
| ✍️ | Manage tasks | Add, edit, complete, and remove tasks. |
| 🔎 | Find what you need | Search tasks and filter completed or all items. |
| 🗓️ | Plan your time | Choose a date, a single time, or a time range. |
| 🔁 | Build a routine | Mark tasks to repeat every day. |
| 🎨 | Make it yours | Switch between light and dark themes and edit local profile details. |
| 📱 | Use it in Persian | Read a right-to-left interface with responsive layouts. |

## Get started

### Use the live app

Open **[nastaranmrz.github.io/today](https://nastaranmrz.github.io/today/)** in a modern browser. There is nothing to install and no sign-up is required.

### Run the downloaded file

1. Download `index.html` from this repository.
2. Open it in a modern browser.

This is a static, single-file app. There is no build step or package installation. The Vazirmatn typeface is loaded from Google Fonts; when it cannot be reached, the browser falls back to a system font.

## How your data is stored

Tasks, theme preferences, and profile details are saved in the browser's `localStorage` on your device. The app does not provide cloud sync, so this information does not automatically move between browsers or devices.

- Reopen the app in the same browser to find your saved data.
- Clearing the site's browser data may remove it.
- Avoid entering sensitive information into a demo or shared device.

## Project map

```text
today/
├── index.html    # App markup, styles, and behavior
├── README.md     # Project overview and getting started
├── TESTING.md    # Manual scenarios and execution notes (Persian)
└── .nojekyll     # GitHub Pages configuration
```

## Quality checks

The manual guide covers task creation and editing, search, filters, date and time selection, navigation, and known follow-up checks. See **[TESTING.md](TESTING.md)** for steps, success criteria, previous observations, and scenarios that still need a real mobile device.

## Feedback

Found something confusing or broken? [Open an issue](https://github.com/Nastaranmrz/today/issues) with the browser and device you used, steps to reproduce it, and what you expected to happen.

## License

No license has been added to this repository yet. Until one is chosen, reuse and redistribution terms are not specified.