### Jenkins的xUnit解析错误与解决02

现象: Junit解析xml文件如下如下错误

日志：

```
11:52:56 INFO: Processing JUnit
11:52:56 INFO: [JUnit] - 1 test report file(s) were found with the pattern '**\00_SW\00_SW_DEV\misc\pts_test\sanity_test\test_report\*.xml' relative to 'D:\Jenkins\workspace\Jenkins_Build_Test' for the testing framework 'JUnit'.
11:52:56 ERROR: Build step failed with exception
11:52:56 java.lang.NullPointerException
11:52:56     at org.jenkinsci.plugins.xunit.XUnitProcessor.recordTestResult(XUnitProcessor.java:354)
11:52:56     at org.jenkinsci.plugins.xunit.XUnitProcessor.process(XUnitProcessor.java:157)
11:52:56     at org.jenkinsci.plugins.xunit.XUnitPublisher.perform(XUnitPublisher.java:161)
11:52:56     at hudson.tasks.BuildStepCompatibilityLayer.perform(BuildStepCompatibilityLayer.java:81)
11:52:56     at hudson.tasks.BuildStepMonitor$1.perform(BuildStepMonitor.java:20)
11:52:56     at hudson.model.AbstractBuild$AbstractBuildExecution.perform(AbstractBuild.java:744)
11:52:56     at hudson.model.AbstractBuild$AbstractBuildExecution.performAllBuildSteps(AbstractBuild.java:690)
11:52:56     at hudson.model.Build$BuildExecution.post2(Build.java:186)
11:52:56     at hudson.model.AbstractBuild$AbstractBuildExecution.post(AbstractBuild.java:635)
11:52:56     at hudson.model.Run.execute(Run.java:1819)
11:52:56     at hudson.model.FreeStyleBuild.run(FreeStyleBuild.java:43)
11:52:56     at hudson.model.ResourceController.execute(ResourceController.java:97)
11:52:56     at hudson.model.Executor.run(Executor.java:429)
11:52:56 Build step 'Publish xUnit test result report' marked build as failure
```

解决：

任务--配置--Process xUnit test result report

把Stop and set the build status to failed if there are errors when processing a result file前的单选框取消

