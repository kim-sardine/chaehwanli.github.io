---
layout : post
title : Usecase of audio storage Manager
---

# Requirement
> Audio Storage에 저장된 녹음된 Audio를 managing 하기 위한 System이 필요하다.
 
# Use Case #1
## Name
Registry Audio
## Brief Description
녹음된 Audio 를 audio storage manager system에 등록한다.
## Actors
Authorized User, Storage System
## Preconditions
well defined MetaData 
|item   | description(sample data)  |
|---|---|
|storage_path |녹음된 Audio가 저장된 storage|
|gender |male, female, ...|
|place_condition |bathrooom, bedroom, liviingroom, ...|
|age |baby, kids, young, adult, senior, ...|
|locale|ko_KR, en_US, en_IN, fr_FR, ...|
## Basic Flow
1. login
2. registry Audio
## Alternate Flows
None
## Exception Flows
storage path is not available
## Post Conditions

# Use Case #2
## Name
Search Audio
## Brief Description
Search Audio
## Actors
Authorized User, Audio Downloader, Storage System
## Preconditions
None
## Basic Flow
1. authorization
2. search Audio with Metadata
## Alternate Flows
None
## Exception Flows
storage system is not avaiable
## Post Conditions
Nnoe

# Use Case #3
## Name
Download Audio
## Brief Description
Download Audio
## Actors
Audio Downloader, Storage System
## Preconditions
None
## Basic Flow
1. authorization
2. download audio
## Alternate Flows
None
## Exception Flows
storage system is not avaiable
## Post Conditions
None

# Use Case Diagram
![usecase_audio_storage](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/chaehwanli/chaehwanli.github.io/gh-pages/plantuml/usecase_audio_storage_manager.iuml)
