# Gradle 'Could not import Ant build file' (ClassCastException)

## How to reproduce

1. `gradle build`
2. Change `buildSrc/src/main/groovy/change_me_to_break_ant.groovy` (set `changeMeToBreakAnt` to 2 for example)
3. `gradle build --stacktrace`

## Workaround

Restart gradle daemon (`gradle --stop && gradle build`)

## Output

```
Parallel execution with configuration on demand is an incubating feature.
:buildSrc:compileJava NO-SOURCE
:buildSrc:compileGroovy UP-TO-DATE
:buildSrc:processResources NO-SOURCE
:buildSrc:classes UP-TO-DATE
:buildSrc:jar UP-TO-DATE
:buildSrc:assemble UP-TO-DATE
:buildSrc:compileTestJava NO-SOURCE
:buildSrc:compileTestGroovy NO-SOURCE
:buildSrc:processTestResources NO-SOURCE
:buildSrc:testClasses UP-TO-DATE
:buildSrc:test NO-SOURCE
:buildSrc:check UP-TO-DATE
:buildSrc:build UP-TO-DATE

FAILURE: Build failed with an exception.

* Where:
Build file 'C:\Users\walthema\git\gradle-ant-classcastexception\build.gradle' line: 1

* What went wrong:
A problem occurred evaluating root project 'gradle-ant-classcastexception'.
> Could not import Ant build file 'C:\Users\walthema\git\gradle-ant-classcastexception\build.xml'.

* Try:
Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Exception is:
org.gradle.api.GradleScriptException: A problem occurred evaluating root project 'gradle-ant-classcastexception'.
        at org.gradle.groovy.scripts.internal.DefaultScriptRunnerFactory$ScriptRunnerImpl.run(DefaultScriptRunnerFactory.java:92)
        at org.gradle.configuration.DefaultScriptPluginFactory$ScriptPluginImpl$2.run(DefaultScriptPluginFactory.java:204)
        at org.gradle.configuration.ProjectScriptTarget.addConfiguration(ProjectScriptTarget.java:77)
        at org.gradle.configuration.DefaultScriptPluginFactory$ScriptPluginImpl.apply(DefaultScriptPluginFactory.java:209)
        at org.gradle.configuration.BuildOperationScriptPlugin$1.run(BuildOperationScriptPlugin.java:61)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:336)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:328)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:199)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:110)
        at org.gradle.configuration.BuildOperationScriptPlugin.apply(BuildOperationScriptPlugin.java:58)
        at org.gradle.configuration.project.BuildScriptProcessor.execute(BuildScriptProcessor.java:41)
        at org.gradle.configuration.project.BuildScriptProcessor.execute(BuildScriptProcessor.java:26)
        at org.gradle.configuration.project.ConfigureActionsProjectEvaluator.evaluate(ConfigureActionsProjectEvaluator.java:34)
        at org.gradle.configuration.project.LifecycleProjectEvaluator.doConfigure(LifecycleProjectEvaluator.java:64)
        at org.gradle.configuration.project.LifecycleProjectEvaluator.access$100(LifecycleProjectEvaluator.java:34)
        at org.gradle.configuration.project.LifecycleProjectEvaluator$ConfigureProject.run(LifecycleProjectEvaluator.java:110)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:336)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:328)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:199)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:110)
        at org.gradle.configuration.project.LifecycleProjectEvaluator.evaluate(LifecycleProjectEvaluator.java:50)
        at org.gradle.api.internal.project.DefaultProject.evaluate(DefaultProject.java:667)
        at org.gradle.api.internal.project.DefaultProject.evaluate(DefaultProject.java:136)
        at org.gradle.execution.TaskPathProjectEvaluator.configure(TaskPathProjectEvaluator.java:35)
        at org.gradle.configuration.DefaultBuildConfigurer.configure(DefaultBuildConfigurer.java:36)
        at org.gradle.initialization.DefaultGradleLauncher$ConfigureBuild.run(DefaultGradleLauncher.java:261)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:336)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:328)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:199)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:110)
        at org.gradle.initialization.DefaultGradleLauncher.configureBuild(DefaultGradleLauncher.java:173)
        at org.gradle.initialization.DefaultGradleLauncher.doBuildStages(DefaultGradleLauncher.java:132)
        at org.gradle.initialization.DefaultGradleLauncher.executeTasks(DefaultGradleLauncher.java:115)
        at org.gradle.internal.invocation.GradleBuildController$1.call(GradleBuildController.java:78)
        at org.gradle.internal.invocation.GradleBuildController$1.call(GradleBuildController.java:75)
        at org.gradle.internal.work.DefaultWorkerLeaseService.withLocks(DefaultWorkerLeaseService.java:152)
        at org.gradle.internal.invocation.GradleBuildController.doBuild(GradleBuildController.java:100)
        at org.gradle.internal.invocation.GradleBuildController.run(GradleBuildController.java:75)
        at org.gradle.tooling.internal.provider.ExecuteBuildActionRunner.run(ExecuteBuildActionRunner.java:28)
        at org.gradle.launcher.exec.ChainingBuildActionRunner.run(ChainingBuildActionRunner.java:35)
        at org.gradle.tooling.internal.provider.ValidatingBuildActionRunner.run(ValidatingBuildActionRunner.java:32)
        at org.gradle.launcher.exec.RunAsBuildOperationBuildActionRunner$1.run(RunAsBuildOperationBuildActionRunner.java:43)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:336)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:328)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:199)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:110)
        at org.gradle.launcher.exec.RunAsBuildOperationBuildActionRunner.run(RunAsBuildOperationBuildActionRunner.java:40)
        at org.gradle.tooling.internal.provider.SubscribableBuildActionRunner.run(SubscribableBuildActionRunner.java:51)
        at org.gradle.launcher.exec.InProcessBuildActionExecuter.execute(InProcessBuildActionExecuter.java:49)
        at org.gradle.launcher.exec.InProcessBuildActionExecuter.execute(InProcessBuildActionExecuter.java:32)
        at org.gradle.launcher.exec.BuildTreeScopeBuildActionExecuter.execute(BuildTreeScopeBuildActionExecuter.java:39)
        at org.gradle.launcher.exec.BuildTreeScopeBuildActionExecuter.execute(BuildTreeScopeBuildActionExecuter.java:25)
        at org.gradle.tooling.internal.provider.ContinuousBuildActionExecuter.execute(ContinuousBuildActionExecuter.java:80)
        at org.gradle.tooling.internal.provider.ContinuousBuildActionExecuter.execute(ContinuousBuildActionExecuter.java:53)
        at org.gradle.tooling.internal.provider.ServicesSetupBuildActionExecuter.execute(ServicesSetupBuildActionExecuter.java:57)
        at org.gradle.tooling.internal.provider.ServicesSetupBuildActionExecuter.execute(ServicesSetupBuildActionExecuter.java:32)
        at org.gradle.tooling.internal.provider.GradleThreadBuildActionExecuter.execute(GradleThreadBuildActionExecuter.java:36)
        at org.gradle.tooling.internal.provider.GradleThreadBuildActionExecuter.execute(GradleThreadBuildActionExecuter.java:25)
        at org.gradle.tooling.internal.provider.ParallelismConfigurationBuildActionExecuter.execute(ParallelismConfigurationBuildActionExecuter.java:43)
        at org.gradle.tooling.internal.provider.ParallelismConfigurationBuildActionExecuter.execute(ParallelismConfigurationBuildActionExecuter.java:29)
        at org.gradle.tooling.internal.provider.StartParamsValidatingActionExecuter.execute(StartParamsValidatingActionExecuter.java:64)
        at org.gradle.tooling.internal.provider.StartParamsValidatingActionExecuter.execute(StartParamsValidatingActionExecuter.java:29)
        at org.gradle.tooling.internal.provider.SessionFailureReportingActionExecuter.execute(SessionFailureReportingActionExecuter.java:59)
        at org.gradle.tooling.internal.provider.SessionFailureReportingActionExecuter.execute(SessionFailureReportingActionExecuter.java:44)
        at org.gradle.tooling.internal.provider.SetupLoggingActionExecuter.execute(SetupLoggingActionExecuter.java:45)
        at org.gradle.tooling.internal.provider.SetupLoggingActionExecuter.execute(SetupLoggingActionExecuter.java:30)
        at org.gradle.launcher.daemon.server.exec.ExecuteBuild.doBuild(ExecuteBuild.java:67)
        at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:36)
        at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:122)
        at org.gradle.launcher.daemon.server.exec.WatchForDisconnection.execute(WatchForDisconnection.java:37)
        at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:122)
        at org.gradle.launcher.daemon.server.exec.ResetDeprecationLogger.execute(ResetDeprecationLogger.java:26)
        at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:122)
        at org.gradle.launcher.daemon.server.exec.RequestStopIfSingleUsedDaemon.execute(RequestStopIfSingleUsedDaemon.java:34)
        at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:122)
        at org.gradle.launcher.daemon.server.exec.ForwardClientInput$2.call(ForwardClientInput.java:74)
        at org.gradle.launcher.daemon.server.exec.ForwardClientInput$2.call(ForwardClientInput.java:72)
        at org.gradle.util.Swapper.swap(Swapper.java:38)
        at org.gradle.launcher.daemon.server.exec.ForwardClientInput.execute(ForwardClientInput.java:72)
        at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:122)
        at org.gradle.launcher.daemon.server.exec.LogAndCheckHealth.execute(LogAndCheckHealth.java:55)
        at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:122)
        at org.gradle.launcher.daemon.server.exec.LogToClient.doBuild(LogToClient.java:62)
        at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:36)
        at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:122)
        at org.gradle.launcher.daemon.server.exec.EstablishBuildEnvironment.doBuild(EstablishBuildEnvironment.java:82)
        at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:36)
        at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:122)
        at org.gradle.launcher.daemon.server.exec.StartBuildOrRespondWithBusy$1.run(StartBuildOrRespondWithBusy.java:50)
        at org.gradle.launcher.daemon.server.DaemonStateCoordinator$1.run(DaemonStateCoordinator.java:295)
        at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
        at org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
        at org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
Caused by: org.gradle.api.GradleException: Could not import Ant build file 'C:\Users\walthema\git\gradle-ant-classcastexception\build.xml'.
        at org.gradle.api.internal.project.DefaultAntBuilder.importBuild(DefaultAntBuilder.java:107)
        at build_58q01z6ce78h8651jabdf5ixa.run(C:\Users\walthema\git\gradle-ant-classcastexception\build.gradle:1)
        at org.gradle.groovy.scripts.internal.DefaultScriptRunnerFactory$ScriptRunnerImpl.run(DefaultScriptRunnerFactory.java:90)
        ... 92 more
Caused by: java.lang.ClassCastException: org.apache.xerces.parsers.XIncludeAwareParserConfiguration cannot be cast to org.apache.xerces.xni.parser.XMLParserConfiguration
        at org.apache.xerces.parsers.SAXParser.<init>(Unknown Source)
        at org.apache.xerces.parsers.SAXParser.<init>(Unknown Source)
        at org.apache.xerces.jaxp.SAXParserImpl$JAXPSAXParser.<init>(Unknown Source)
        at org.apache.xerces.jaxp.SAXParserImpl.<init>(Unknown Source)
        at org.apache.xerces.jaxp.SAXParserFactoryImpl.newSAXParser(Unknown Source)
        at org.apache.tools.ant.util.JAXPUtils.newSAXParser(JAXPUtils.java:217)
        at org.apache.tools.ant.util.JAXPUtils.getNamespaceXMLReader(JAXPUtils.java:174)
        at org.apache.tools.ant.helper.ProjectHelper2.parse(ProjectHelper2.java:245)
        at org.apache.tools.ant.helper.ProjectHelper2.parse(ProjectHelper2.java:178)
        at org.apache.tools.ant.ProjectHelper.configureProject(ProjectHelper.java:93)
        at org.gradle.api.internal.project.DefaultAntBuilder.importBuild(DefaultAntBuilder.java:105)
        ... 94 more


* Get more help at https://help.gradle.org

BUILD FAILED in 2s
```
