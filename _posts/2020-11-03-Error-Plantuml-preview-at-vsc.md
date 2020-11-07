---
layout : post
title : write EPIPE error is happened when plantuml previews at visual studio code
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
> Java is not installed yet!
[Installed tools for my notebook](https://chaehwanli.github.io/2020/11/03/Installed-tools-for-my-notebook/)

4. test java and plantuml.jar
> plantuml.jar is located in extention is installed 
> C:\Users\chaeh\.vscode\extensions\jebbs.plantuml-2.13.14>java -jar plantuml.jar C:\GitHubRepo\chaehwanli.github.io\plantuml\amq
No diagram found
> C:\Users\chaeh\.vscode\extensions\jebbs.plantuml-2.13.14>java -jar plantuml.jar C:\GitHubRepo\chaehwanli.github.io\plantuml\amqp_apiserver_engineserver.iuml


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
> C:\Users\chaeh\.vscode\extensions\jebbs.plantuml-2.13.14>java -jar plantuml.jar -testdot C:\GitHubRepo\chaehwanli.github.io\plantuml\amqp_apiserver_engineserver.iuml   
Error: No dot executable found
Error: only sequence diagrams will be generated

7. install Graphviz
> install [Graphviz](https://graphviz.org/download/)
https://www2.graphviz.org/Packages/stable/windows/10/cmake/Release/x64/

8. error page
> ![error page](..\images\graphviz_dot_error_2.png)

9. there is error about "dot"
```
C:\Users\chaeh>dot -v
dot - graphviz version 2.44.1 (20200629.0846)
There is no layout engine support for "dot"
Perhaps "dot -c" needs to be run (with installer's privileges) to register the plugins?
C:\Users\chaeh>dot -c
Error: failed to open C:\Program Files\Graphviz 2.44.1\bin\config6 for write.
```
> https://forum.plantuml.net/11828/for-some-reason-dot-graphviz-has-crashed(https://forum.plantuml.net/11828/for-some-reason-dot-graphviz-has-crashed)

- in a browser goto https://www2.graphviz.org/Packages/stable/windows/10/msbuild/Release/Win32/
- download the graphviz-2.44.1-win32.zip
- open the downloaded zip file and place the bin directory somewhere on your system

10. run again
```
C:\Users\chaeh>dot -v
dot - graphviz version 2.44.1 (20200629.0800)
libdir = "C:\Program Files\Graphviz 2.44.1\bin"
Activated plugin library: gvplugin_dot_layout.dll
Using layout: dot:dot_layout
Activated plugin library: gvplugin_core.dll
Using render: dot:core
Using device: dot:dot:core
The plugin configuration file:
        C:\Program Files\Graphviz 2.44.1\bin\config6
                was successfully loaded.
    render      :  cairo dot dot_json fig gd gdiplus json json0 map mp pic pov ps svg tk vml vrml xdot xdot_json
    layout      :  circo dot fdp neato nop nop1 nop2 osage patchwork sfdp twopi
    textlayout  :  textlayout
    device      :  bmp canon cmap cmapx cmapx_np dot dot_json emf emfplus eps fig gd gd2 gif gv imap imap_np ismap jpe jpeg jpg json json0 metafile mp pdf pic plain plain-ext png pov ps ps2 svg svgz tif tiff tk vml vmlz vrml wbmp xdot xdot1.2 xdot1.4 xdot_json
    loadimage   :  (lib) bmp eps gd gd2 gif jpe jpeg jpg png ps svg
C:\Users\chaeh>dot -c
C:\Users\chaeh>
```

11. Success
> Alt+D on .iuml file editor
![success](..\images\plantuml_preview_in_vsc.png)