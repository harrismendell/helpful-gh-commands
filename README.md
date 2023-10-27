README.md

# Helpful GitHub CLI Commands

## List review requests across all repos
```
gh alias set r "search prs --state=open --review-requested=@me --involves=@me --json repository,number,title,url,updatedAt --template '{{range .}}{{tablerow .repository.name (.number | autocolor \"green\") .title (.url | autocolor \"cyan\") (timeago .updatedAt)}}{{end}}'"
```

`gh r` will now provide a list of all open review requests assigned to you across all repos, with links to said prs. It will only show prs that you are directly set as a reviewer for. (It will omit prs that are assigned to a group that you belong to). To change this behavior remove the --involves flag.

##  List open PRs you've authored across all repos
```
gh alias set p "search prs --state=open --author=@me --json repository,number,title,url,updatedAt --template '{{range .}}{{tablerow .repository.name (.number | autocolor \"green\") .title (.url | autocolor \"cyan\") (timeago .updatedAt)}}{{end}}'"
```

`gh p` will now provide a list of prs you've authored across all repos
