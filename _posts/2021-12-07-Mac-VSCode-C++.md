---
layout: post
title:  "[Mac] VSCode & C/C++"
date:   2021-12-07 23:00:00 +0900
categories: [mac]
---

#### VSCode 참조문서
[https://code.visualstudio.com/docs/?dv=osx](https://code.visualstudio.com/docs/?dv=osx)

<br>

#### VSCode 설치
```bash
brew install cask
brew install –cask visual-studio-code
g++ -v
lldb
```
<br>

#### VScode Extension 설치
```bash
Extension:CodeLLDB
```
<br>

#### VSCode 셋업
`Cmd+Shift+B` -> `C/C++:g++ build activate file`
`Cmd+Shift+B` -> `Config` -> `.vscode/tasks.json`
```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;
int main()
{
  vector<string> msg; //{"Hello", "C++", "World", "from", "VSCode"};
  msg.push_back("Hello");
  msg.push_back("C++");
  for (const string &word : msg)
  {
    cout << word << " ";
  }
  cout << endl;
  return 0;
}
```
```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "type": "cppbuild",
      "label": "C/C++: g++ 활성 파일 빌드",
      "command": "/usr/bin/g++",
      "args": [
        "-std=c++17", 
        "-stdlib=libc++", 
        "-g",
        "${file}",
        "-o",
        "${fileDirname}/${fileBasenameNoExtension}"
        //"<",
        //"${fileDirname}/input.txt",
        //">",
        //"${fileDirname}/output.txt"
      ],
      "options": {
        "cwd": "${fileDirname}"
      },
      "problemMatcher": [
        "$gcc"
      ],
      "group": "build",
      "detail": "컴파일러: /usr/bin/g++"
    }
  ]
}
```

`Fn+F5` -> `.vscode/launch.json`
```json
{
  // IntelliSense를 사용하여 가능한 특성에 대해 알아보세요.
  // 기존 특성에 대한 설명을 보려면 가리킵니다.
  // 자세한 내용을 보려면 https://go.microsoft.com/fwlink/?linkid=830387을(를) 방문하세요.
  "version": "0.2.0",
  "configurations": [
    {
      "name": "g++ - 활성 파일 빌드 및 디버그",
      "type": "lldb",
      "request": "launch",
      "program": "${fileDirname}/${fileBasenameNoExtension}",
      "args": [],
      "stopAtEntry": false,
      "cwd": "${fileDirname}",
      "environment": [],
      "externalConsole": false,
      "MIMode": "lldb",
      "preLaunchTask": "C/C++: g++ 활성 파일 빌드"
    }
  ]
}
```
