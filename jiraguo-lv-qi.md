### Jira过滤器

```
上周工作内容
assignee = currentUser() AND status != Open AND status != Closed AND updatedDate >= startOfWeek(-1) ORDER BY updatedDate

上月工作内容
assignee = currentUser() AND status != Open AND status != Closed AND updatedDate >= startOfMonth(-1) ORDER BY updatedDate

这周工作内容
assignee = currentUser() AND status != Open AND status != Closed AND updatedDate >= startOfWeek() ORDER BY updatedDate

这月工作内容
assignee = currentUser() AND status != Open AND status != Closed AND updatedDate >= startOfMonth() ORDER BY updatedDate

当前工作内容
status = "In Progress" AND resolution = Unresolved AND assignee in (currentUser()) ORDER BY updated DESC

由我提交的问题
reporter = currentUser() order by created DESC

分配给我的未解决问题
assignee = currentUser() AND resolution = Unresolved order by updated DESC
```



