# Description
Fetches a Jira ticket by ID and explains it to you.

# Instructions
When this command is invoked with a ticket ID (e.g., /jira AH-972):
1. Extract the ticket ID from the arguments.
2. Use the Atlassian MCP server to fetch the details of the Jira ticket.
3. You must use the `mcp_atlassian_getJiraIssue` tool from the MCP server with the `issueIdOrKey` argument set to the provided ticket ID.
4. You must pass the correct `cloudId` argument to the tool: `f402e97d-af06-4011-8ae6-478d847f5626`.
5. Once you retrieve the ticket details, present a clear, structured markdown summary of the ticket. The summary should include:
   - Ticket Key and Title
   - Type, Status, Priority
   - Assignee and Reporter
   - A detailed breakdown of the Problem Statement / Description
   - Acceptance Criteria (if any)
   - Any other relevant fields.
6. Do NOT just dump the JSON output. Format it nicely into a readable report.
