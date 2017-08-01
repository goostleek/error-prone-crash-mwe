# error-prone-crash-mwe
This is an [MWE](https://www.wikiwand.com/en/Minimal_Working_Example) for errror-prone compiler bug that causes crash under gradle.

To reproduce the bug just run the
```bash
./gradlew build
```

The result should be

```
> Task :compileJava
C:\work\error-prone-crash-mwe\src\main\java\com\google\errorprone\Crash.java:5: error: An unhandled exception was thrown by the Error Prone static analysis plugin.
@Value
^
     Please report this at https://github.com/google/error-prone/issues/new and include the following:

     error-prone version: 2.0.21
     Stack Trace:
     java.lang.ClassCastException: com.sun.tools.javac.tree.JCTree$JCBinary cannot be cast to com.sun.source.tree.ParenthesizedTree
        at com.google.errorprone.bugpatterns.NestedInstanceOfConditions.matchIf(NestedInstanceOfConditions.java:53)
        at com.google.errorprone.scanner.ErrorProneScanner.visitIf(ErrorProneScanner.java:752)
        at com.google.errorprone.scanner.ErrorProneScanner.visitIf(ErrorProneScanner.java:146)
        at com.sun.tools.javac.tree.JCTree$JCIf.accept(JCTree.java:1427)
        at com.sun.source.util.TreePathScanner.scan(TreePathScanner.java:82)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:82)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:42)
        at com.sun.source.util.TreeScanner.scan(TreeScanner.java:105)
        at com.sun.source.util.TreeScanner.visitBlock(TreeScanner.java:248)
        at com.google.errorprone.scanner.ErrorProneScanner.visitBlock(ErrorProneScanner.java:530)
        at com.google.errorprone.scanner.ErrorProneScanner.visitBlock(ErrorProneScanner.java:146)
        at com.sun.tools.javac.tree.JCTree$JCBlock.accept(JCTree.java:1026)
        at com.sun.source.util.TreePathScanner.scan(TreePathScanner.java:82)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:82)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:42)
        at com.sun.source.util.TreeScanner.scanAndReduce(TreeScanner.java:90)
        at com.sun.source.util.TreeScanner.visitMethod(TreeScanner.java:206)
        at com.google.errorprone.scanner.ErrorProneScanner.visitMethod(ErrorProneScanner.java:898)
        at com.google.errorprone.scanner.ErrorProneScanner.visitMethod(ErrorProneScanner.java:146)
        at com.sun.tools.javac.tree.JCTree$JCMethodDecl.accept(JCTree.java:898)
        at com.sun.source.util.TreePathScanner.scan(TreePathScanner.java:82)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:82)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:42)
        at com.sun.source.util.TreeScanner.scanAndReduce(TreeScanner.java:90)
        at com.sun.source.util.TreeScanner.scan(TreeScanner.java:105)
        at com.sun.source.util.TreeScanner.scanAndReduce(TreeScanner.java:113)
        at com.sun.source.util.TreeScanner.visitClass(TreeScanner.java:187)
        at com.google.errorprone.scanner.ErrorProneScanner.visitClass(ErrorProneScanner.java:590)
        at com.google.errorprone.scanner.ErrorProneScanner.visitClass(ErrorProneScanner.java:146)
        at com.sun.tools.javac.tree.JCTree$JCClassDecl.accept(JCTree.java:808)
        at com.sun.source.util.TreePathScanner.scan(TreePathScanner.java:82)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:82)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:42)
        at com.sun.source.util.TreeScanner.scan(TreeScanner.java:105)
        at com.sun.source.util.TreeScanner.scanAndReduce(TreeScanner.java:113)
        at com.sun.source.util.TreeScanner.visitCompilationUnit(TreeScanner.java:144)
        at com.google.errorprone.scanner.ErrorProneScanner.visitCompilationUnit(ErrorProneScanner.java:605)
        at com.google.errorprone.scanner.ErrorProneScanner.visitCompilationUnit(ErrorProneScanner.java:146)
        at com.sun.tools.javac.tree.JCTree$JCCompilationUnit.accept(JCTree.java:591)
        at com.sun.source.util.TreePathScanner.scan(TreePathScanner.java:56)
        at com.google.errorprone.scanner.Scanner.scan(Scanner.java:64)
        at com.google.errorprone.scanner.ErrorProneScannerTransformer.apply(ErrorProneScannerTransformer.java:41)
        at com.google.errorprone.ErrorProneAnalyzer.finished(ErrorProneAnalyzer.java:145)
        at com.sun.tools.javac.api.MultiTaskListener.finished(MultiTaskListener.java:120)
        at com.sun.tools.javac.main.JavaCompiler.flow(JavaCompiler.java:1425)
        at com.sun.tools.javac.main.JavaCompiler.flow(JavaCompiler.java:1374)
        at com.sun.tools.javac.main.JavaCompiler.compile(JavaCompiler.java:973)
        at com.sun.tools.javac.api.JavacTaskImpl.lambda$doCall$0(JavacTaskImpl.java:100)
        at com.sun.tools.javac.api.JavacTaskImpl.handleExceptions(JavacTaskImpl.java:142)
        at com.sun.tools.javac.api.JavacTaskImpl.doCall(JavacTaskImpl.java:96)
        at com.sun.tools.javac.api.JavacTaskImpl.call(JavacTaskImpl.java:90)
        at com.google.errorprone.BaseErrorProneCompiler.run(BaseErrorProneCompiler.java:137)
        at com.google.errorprone.BaseErrorProneCompiler.run(BaseErrorProneCompiler.java:108)
        at com.google.errorprone.ErrorProneCompiler.run(ErrorProneCompiler.java:118)
        at com.google.errorprone.ErrorProneCompiler.compile(ErrorProneCompiler.java:65)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:498)
        at net.ltgt.gradle.errorprone.ErrorProneCompiler.execute(ErrorProneCompiler.java:63)
        at net.ltgt.gradle.errorprone.ErrorProneCompiler.execute(ErrorProneCompiler.java:24)
        at org.gradle.api.internal.tasks.compile.NormalizingJavaCompiler.delegateAndHandleErrors(NormalizingJavaCompiler.java:99)
        at org.gradle.api.internal.tasks.compile.NormalizingJavaCompiler.execute(NormalizingJavaCompiler.java:52)
        at org.gradle.api.internal.tasks.compile.NormalizingJavaCompiler.execute(NormalizingJavaCompiler.java:37)
        at org.gradle.api.internal.tasks.compile.CleaningJavaCompilerSupport.execute(CleaningJavaCompilerSupport.java:35)
        at org.gradle.api.internal.tasks.compile.CleaningJavaCompilerSupport.execute(CleaningJavaCompilerSupport.java:25)
        at org.gradle.api.tasks.compile.JavaCompile.performCompilation(JavaCompile.java:198)
        at org.gradle.api.tasks.compile.JavaCompile.compile(JavaCompile.java:183)
        at org.gradle.api.tasks.compile.JavaCompile.compile(JavaCompile.java:120)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:498)
        at org.gradle.internal.reflect.JavaMethod.invoke(JavaMethod.java:73)
        at org.gradle.api.internal.project.taskfactory.DefaultTaskClassInfoStore$IncrementalTaskAction.doExecute(DefaultTaskClassInfoStore.java:168)
        at org.gradle.api.internal.project.taskfactory.DefaultTaskClassInfoStore$StandardTaskAction.execute(DefaultTaskClassInfoStore.java:134)
        at org.gradle.api.internal.project.taskfactory.DefaultTaskClassInfoStore$StandardTaskAction.execute(DefaultTaskClassInfoStore.java:121)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter$1.run(ExecuteActionsTaskExecuter.java:122)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:317)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:309)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:185)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:95)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeAction(ExecuteActionsTaskExecuter.java:111)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeActions(ExecuteActionsTaskExecuter.java:92)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.execute(ExecuteActionsTaskExecuter.java:70)
        at org.gradle.api.internal.tasks.execution.SkipUpToDateTaskExecuter.execute(SkipUpToDateTaskExecuter.java:64)
        at org.gradle.api.internal.tasks.execution.ResolveTaskOutputCachingStateExecuter.execute(ResolveTaskOutputCachingStateExecuter.java:54)
        at org.gradle.api.internal.tasks.execution.ValidatingTaskExecuter.execute(ValidatingTaskExecuter.java:58)
        at org.gradle.api.internal.tasks.execution.SkipEmptySourceFilesTaskExecuter.execute(SkipEmptySourceFilesTaskExecuter.java:88)
        at org.gradle.api.internal.tasks.execution.ResolveTaskArtifactStateTaskExecuter.execute(ResolveTaskArtifactStateTaskExecuter.java:52)
        at org.gradle.api.internal.tasks.execution.SkipTaskWithNoActionsExecuter.execute(SkipTaskWithNoActionsExecuter.java:52)
        at org.gradle.api.internal.tasks.execution.SkipOnlyIfTaskExecuter.execute(SkipOnlyIfTaskExecuter.java:54)
        at org.gradle.api.internal.tasks.execution.ExecuteAtMostOnceTaskExecuter.execute(ExecuteAtMostOnceTaskExecuter.java:43)
        at org.gradle.api.internal.tasks.execution.CatchExceptionTaskExecuter.execute(CatchExceptionTaskExecuter.java:34)
        at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter$EventFiringTaskWorker$1.run(DefaultTaskGraphExecuter.java:242)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:317)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:309)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:185)
        at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:95)
        at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter$EventFiringTaskWorker.execute(DefaultTaskGraphExecuter.java:235)
        at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter$EventFiringTaskWorker.execute(DefaultTaskGraphExecuter.java:224)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker.processTask(DefaultTaskPlanExecutor.java:121)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker.access$200(DefaultTaskPlanExecutor.java:77)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker$1.execute(DefaultTaskPlanExecutor.java:102)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker$1.execute(DefaultTaskPlanExecutor.java:96)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionPlan.execute(DefaultTaskExecutionPlan.java:612)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionPlan.executeWithTask(DefaultTaskExecutionPlan.java:567)
        at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor$TaskExecutorWorker.run(DefaultTaskPlanExecutor.java:96)
        at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
        at org.gradle.internal.concurrent.StoppableExecutorImpl$1.run(StoppableExecutorImpl.java:46)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
        at org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
        at java.lang.Thread.run(Thread.java:748)
1 error


FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':compileJava'.
> Compilation failed with exit code 1; see the compiler error output for details.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output.

BUILD FAILED in 3s
1 actionable task: 1 executed
```
