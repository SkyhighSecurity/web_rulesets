### Setup

- In SSE go to Policy -> Web Policy -> Policy
- Click on "New Ruleset" in the top right corner and select "Custom Ruleset"
- Set the Ruleset name to whatever you like e.g. Perplexity Controls
- Select Criteria:
  URL is "www.perplexity.ai"
  OR
  URL is "api.perplexity.ai"
- Click on "Applies to: All" and unselect "Embedded Objects"
- To import a Rule from this ruleset click on the 3-dot Menu of your ruleset and select "Add Custom Rule" - "Via Policy Code"
- Name the rule like the github file you want to import
- Click on "Edit" and copy and paste the code of the rule into the policy code view
- Click on "Save" to save your rule
  
### Features

This rulesets provides rules for the following actions for the Perplexity Webservice and API:

- Limit prompt Length to x characters by cutting off prompt (Web & API)
- Limit prompt Length by replacing prompt with policy warning when max length is exceeded (Web & API)
- Ensure specific sources (web/scholar/social) are enabled (Web)
- Block specific sources (web/scholar/social) (Web)
- Enforce search mode (auto/pro/reasoning/deep research) (Web)
- Block file upload (Web)
- Block Link Sharing (Web)
- Prevent pasting from Clipboard (Web)
- Block microphone access (Web)
- Block click to Copy (Web)
- Block unauthenticated chats (Web)

<br/><br/>
### Limitations
The "Block Link Sharing" rule only works for blocking the sharing of chats of an authenticated user as chats of unauthenticated users are public by default and can be shared by just copying the link from the browser URL bar.
It will also not block the generation and copying of the link into the clipboard as that happens locally. The rule only blocks the request to update the access configuration of the thread so that the generated link does not work.
You can use the "Block click to copy" rule to disable the copying to clipboard action (but that will also block any other click to copy functionality, for example for code blocks).
You can also use the "Block unauthenticated chats" rule to block any unauthenticated chat requests so anything users might be able to share cannot contain sensitive information.


### Customizing Settings:

Rule: Limit prompt length (WebApp)

Adjust variable "maxPromptLength" based on your requirements

<br/><br/>

Rule: Ensure selected Sources (WebApp)

Adjust variable "ensured_sources" to contain the sources you want to enforce (available sources are "web", "scholar" and "social"

<br/><br/>

Rule: Block selected Sources (WebApp)

Adjust variable "blocked_sources" to contain the sources you want to block (available sources are "web", "scholar" and "social"

<br/><br/>

Rule: Enforce Search Mode (WebApp)

Set the variable "paramsMode" and "paramsModelPreference" variables based on which mode you want to enforce, possible value combinations are described in comments in the policy code

<br/><br/>

Rule: Limit prompt length (API)

Adjust variable "maxPromptLength" based on your requirements

Remove entries for roles for that you do NOT want to limit the prompt length for from the "limitedRoles" variable

<br/><br/>

Rule: Replace prompt (API)

Adjust variable "maxPromptLength" based on your requirements

Remove entries for roles for that you do NOT want to replace the prompt for from the "limitedRoles" variable
