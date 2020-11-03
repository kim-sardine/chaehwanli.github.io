---
layout : post
title : 'write EPIPE' error is happened when plantuml previews at visual studio code
---

# Error Message
```
Error: write EPIPE
at afterWriteDispatched (internal/stream_base_commons.js:149:25)
at writeGeneric (internal/stream_base_commons.js:140:3)
at Socket._writeGeneric (net.js:776:11)
at Socket._write (net.js:788:8)
at doWrite (_stream_writable.js:435:12)
at writeOrBuffer (_stream_writable.js:419:5)
at Socket.Writable.write (_stream_writable.js:309:11)
at c:\Users\chaeh\.vscode\extensions\jebbs.plantuml-2.13.14\out\src\plantuml\renders\local.js:112:35
at runMicrotasks ()
at processTicksAndRejections (internal/process/task_queues.js:94:5)
```

refer to https://github.com/qjebbs/vscode-plantuml/issues/167

1. The settings will not be correted. but I don't know where is settings.
2. anyway follows callstacks
```
at c:\Users\chaeh\.vscode\extensions\jebbs.plantuml-2.13.14\out\src\plantuml\renders\local.js:112:35
```
3. Oops... I didn't install 'Java' yet.

# Java is not installed yet!
[Installed tools for my notebook](https://chaehwanli.github.io/2020/11/03/Installed-tools-for-my-notebook/)

4. test java and plantuml.jar
> plantuml.jar is located in extention is installed 

```
C:\Users\chaeh\.vscode\extensions\jebbs.plantuml-2.13.14>java -jar plantuml.jar C:\GitHubRepo\chaehwanli.github.io\plantuml\amq
No diagram found

C:\Users\chaeh\.vscode\extensions\jebbs.plantuml-2.13.14>java -jar plantuml.jar C:\GitHubRepo\chaehwanli.github.io\plantuml\amqp_apiserver_engineserver.iuml
```

5. Error Message by cli
```
Dot Executable : null
No dot executable found 
Cannot find Graphviz. You should try

@staruml
testdot
@enduml

or
java -jar plantuml.jar -testdot
```

6. try "java -jar plantuml.jar -testdot"
```
C:\Users\chaeh\.vscode\extensions\jebbs.plantuml-2.13.14>java -jar plantuml.jar -testdot C:\GitHubRepo\chaehwanli.github.io\plantuml\amqp_apiserver_engineserver.iuml
Error: No dot executable found
Error: only sequence diagrams will be generated
```

7. install Graphviz
install [Graphviz](https://graphviz.org/download/)
> https://www2.graphviz.org/Packages/stable/windows/10/cmake/Release/x64/

8. error page
![error page](..\images\graphviz_dot_error_2.png)
