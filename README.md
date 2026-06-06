# Residential General Contractor Agent

## Setup
*Example using the Codex CLI*

Got to your project repo, then:
1. Copy the AGENTS.md file at the root of your repo
2. Under your repo, create a ".codex/skills" directory and copy the content of the "Skills" directories in it
3. Under your repo, create an "Intake" directory.
4. Start codex and both the "AGENTS.md" and the skills should load automatically.

## Usage
### Provide Context and Documents
When you are ready to work with the agent, start by copying any relevant reference documents into the "Intake" directory. This includes any project plans, specifications, drawings, bid packages, invoices, and other relevant documents.

### Interact with the Agent
Will act as an advisor but will help by using the following skills:
* gc_setup
  * **Project Initialisation** 
* gc_intake
  * **Bid Intake**
  * **Invoice Intake**
* gc_manage
  * **Milestones Management**
  * **Cost Analysis**

