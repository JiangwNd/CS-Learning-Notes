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
```



