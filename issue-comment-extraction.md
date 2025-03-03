# Extract Issue comments
## GH command to extract comments from all issues in repo into a CSV file
`gh issue list -L 1000 --json number,title,labels,body,comments --jq ' sort_by(.number) | map([ .number, .title, (.labels | map(.name) | join(",")), .body, (.comments
 | map(.body) | join(",")) ])[] | @csv '`
Note/Thought: for the comment, body, join, should I use something like "@" instead to easily find the separation?
