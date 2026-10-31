# Account Connection Troubleshooting

## Diagnose before you repeat a link

- Ask the user what happened after the last attempt before you send the same link again.

- Change the next step when the user says the link did not work instead of repeating the same explanation.

- Check the linked account state through the relevant connector doc before you claim the account is connected or unconnected.

- Compare what the user sees with what the connector reports and name the mismatch in plain words.

## Separate registration from consent

- Treat a profile that appears in an accounts center as registration only and not as consent for Muse.

- Ask whether the user completed the consent step for Muse itself when the account list and the connector disagree.

- Run the connector check again after the user says consent is complete and report only that result.

## Check how the link opens

- Ask which app or browser opened when the user tapped the link.

- Guide the user to turn off open by default for the app that opened the link instead of a browser before you send the link again.

- Ask the user to open the link from a browser address bar rather than from a search box or a chat input when the destination is unclear.

- Confirm the page title or destination the user sees before you move to the next step.

## Stop on a danger screen

- Stop immediately when a screen mentions permanent deletion, deactivation, or removal of the account itself.

- Tell the user not to tap continue on that screen and ask the user to leave that screen.

- Find the separate move or unlink path in the accounts center before you give any further navigation step.

- Verify the exact screen title with the user before you direct the user to a menu that can delete or deactivate an account.

## Verify and hand over cleanly

- Verify the linked state through the connector check after the user finishes the flow.

- Report the linked account by username or display name and the check you used.

- Stop the task when the check confirms the link and do not send further connection links.

- Hand the browser or login step back to the user promptly when a stored credential is rejected instead of resubmitting it.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Offer a fresh link only after you have changed the condition that made the last link fail.

- Offer a different browser or a different device when the link keeps opening in the wrong app.

- Ask a short clarifying question about the exact screen the user sees instead of guessing the next menu.
