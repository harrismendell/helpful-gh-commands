README.md

# Helpful GitHub CLI Commands
Included is a list of [gh cli](https://github.com/cli/cli) commands I find particular useful. You can read and copy them below, or alternatively import them from [aliases.yaml](aliases.yaml) with the command `gh alias import aliases.yaml`.




## List review requests across all repos
```
gh search prs --state=open --review-requested=@me --involves=@me --json repository,number,title,url,updatedAt --template '{{range .}}{{tablerow .repository.name (.number | autocolor "green") .title (.url | autocolor "cyan") (timeago .updatedAt)}}{{end}}'
```

This will only show prs that you are directly set as a reviewer for. (It will omit prs that are assigned to a group that you belong to). To change this behavior remove the --involves flag.

##  List open PRs you've authored across all repos
```
gh search prs --state=open --author=@me --json repository,number,title,url,updatedAt --template '{{range .}}{{tablerow .repository.name (.number | autocolor "green") .title (.url | autocolor "cyan") (timeago .updatedAt)}}{{end}}'
```


