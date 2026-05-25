# PlantSimulation Copilot Skill

A VS Code GitHub Copilot skill for generating Siemens Plant Simulation / SimTalk code and providing modeling guidance, strictly grounded in the official Plant Simulation Help and other documents.

---

## Prerequisites

- [VS Code](https://code.visualstudio.com/) with the [GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat) extension installed and activated
- Git

---

## Installation（一键安装）

Clone this repository **directly** into the VS Code global skills directory. This single command makes the skill available across **all** your workspaces.

**Windows (PowerShell):**

```powershell
git clone https://github.com/zheng-h-4/plantsimulation-copilot-for-vscode "$env:USERPROFILE\.copilot\skills\plantsimulation-copilot"
```

**macOS / Linux:**

```bash
git clone https://github.com/zheng-h-4/plantsimulation-copilot-for-vscode ~/.copilot/skills/plantsimulation-copilot
```

> The folder name `plantsimulation-copilot` at the end of the path must be kept exactly as shown — it matches the skill's internal `name` field and determines the slash-command name.

After cloning, **reload VS Code** (press `Ctrl+Shift+P` → `Developer: Reload Window`) for the skill to be detected.

---

## Usage

Once installed, open GitHub Copilot Chat in VS Code and type:

```
/plantsimulation-copilot <your question or task>
```

For example:

```
/plantsimulation-copilot Write a SimTalk method that logs MU throughput every shift.
```

The skill will automatically load the bundled Plant Simulation Help and Modeling Standards references before generating or reviewing code.

---

## Updating

To pull the latest version of the skill, navigate to the cloned folder and run `git pull`:

**Windows (PowerShell):**

```powershell
cd "$env:USERPROFILE\.copilot\skills\plantsimulation-copilot"
git pull
```

**macOS / Linux:**

```bash
cd ~/.copilot/skills/plantsimulation-copilot
git pull
```

---

## Repository Structure

```
plantsimulation-copilot/
├── SKILL.md                          # Skill definition (loaded by VS Code Copilot)
├── README.md
├── references/                       # Concise summaries for quick in-context lookup
│   ├── simtalk-syntax-quick-ref.md   # SimTalk 2.0 syntax cheat sheet
│   ├── simtalk-api-index.md          # Key API methods index
│   ├── modeling-standards.md         # Core SimTalk / DataTable / naming standards
│   └── knowledge-base-map.md         # Map/index of the full knowledge base
└── knowledge_base/                   # Full markdown knowledge base
    └── pts_help_2504/                # Plant Simulation 2504 official help
        ├── 09_Plant_Simulation_Program_Window/
        ├── 10_Step-by-Step_Help/
        ├── 11_Objects_Reference_Help/
        ├── 12_SimTalk_Reference/
        ├── 13_3D_Reference_Help/
        └── 15_Add-Ins_Reference_Help/
```
