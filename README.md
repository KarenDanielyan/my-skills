# my-skills

This repository contains a collection of custom skills for AI coding assistants. Each skill is designed to guide the assistant on how to perform specific tasks using predefined templates, rules, and workflows.

## 🗂️ Skills Directory

Below is an index of the available skills in this workspace:

| Skill | Path / Reference | Description | Triggers & Keywords |
| :--- | :--- | :--- | :--- |
| **matlab-header-formatter** | [matlab-header-formatter/SKILL.md](file:///C:/Users/kdaniely/Desktop/my-skills/matlab-header-formatter/SKILL.md) | Generates and formats standardized MATLAB file headers for classes, class methods, and standalone functions including a custom logo block. | `add a header to this MATLAB file`, `format the header`, `write a MATLAB function header`, `document this class`, `add MATLAB documentation` |

---

## 🛠️ Skill Installation

This is guide is for installing skills in Google Antigravity.

To install one of the skills from this repository, copy the skill's folder (e.g., `matlab-header-formatter`) into one of the designated Antigravity directories depending on your desired scope:

*   **Workspace-Specific Skills** (Available only within this project):
    Copy the folder to the [skills](file:///C:/Users/<username>/<path-to-workspace>/.agents/skills/) directory:
    `<workspace-root>/.agents/skills/`
    *(Note: Older versions of Antigravity may scan `.agent/skills/` instead).*
    
*   **Global Skills** (Available across all of your projects):
    Copy the folder to your global config directory:
    `~/.gemini/config/skills/`

Once placed in either directory, the agent will automatically discover the skill during your next conversation.
