# Runtime Issue Lifetime Management Process

Goal of issue triaging is to manage an issue effectively throughout the lifetime of the issue from open to close and communicate the status of it to relevant participants such as author, assignee(s), commenter(s), area owner(s) and team(s). Triaging an issue is performed collaboratively by dotnet-issue-labeler bot, msftbot, feature area owners and team members. We try to triage an issue immediately via our dotnet-issue-labeler bot by assigning an area but may take longer if the bot cannot determine an area to assign. If the bot cannot determine the area, runtime owner will manually assign an area. The bot also initially puts `untriaged` label to the issue.
Once an area is assigned, area owner will further triage it by assigning milestone and optionally assignee. If the area owner cannot determine the milestone immediately, for example, because more investigation is needed, the area owner will remove untriaged label and put needs-further-triage label. When an issue is successfully triaged, it will be assigned an area, milestone and optionally assignee. When the assigned milestone is not specific product but future, it means that it will be kept as backlog.

[Placeholder] bot related info
[Placeholder] Info on runtime area owners can be found in https://github.com/dotnet/runtime/blob/main/docs/area-owners.md. 
