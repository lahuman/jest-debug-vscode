# VSCode에서 Jest Debug 설정

> 테스트 케이스를 실행 중 에러가 발생했습니다. 이를 해결하기 위해서는 console.log 만으론 부족하여서, jest + debug 처리를 해보았습니다.

## 시작하기 
vscode에서 왼쪽에 ```run to debug``` 버튼을 클릭하여, ```Run and Debug``` 버튼을 클릭하여 ```.vscode``` 디렉토리 와 ```launch.json``` 파일을 생성합니다. 

```launch.json``` 파일은 아래와 같은 설정을 가집니다 .

```javascript
{
  "version": "1.0.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Jest: current file",
      "program": "${workspaceFolder}/node_modules/jest-cli/bin/jest.js",
      "args": ["--config", "./test/jest-e2e.json"],
      "console": "integratedTerminal",
      "disableOptimisticBPs": true,
      "windows": {
        "program": "${workspaceFolder}/node_modules/jest/bin/jest"
      }
    }
  ]
}
```

필요에 의해서 ```args``` 의 값을 변경하여 실행 할 수 있습니다.

아래는 여러 옵션을 추가한 예제 입니다. 

```javascript
  "args": ["--runInBand", "--config", "./test/jest-e2e.json", "--testRegex", "./test/user.e2e-spec.ts", "--forceExit"],
```

> 더욱 자세한 설정은 [Debugging in VS Code](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations) 또는 [Node.js debugging in VS Code](https://code.visualstudio.com/docs/nodejs/nodejs-debugging#_launch-configuration-attributes)


## deguggin 시작하기 

1. breakpoint를 확인하려는 코드에 설정
2. ```Ctrl + Shift + D``` 또는 왼쪽에 ```Run and Debug``` 메뉴 선택
3. 상단에서 실행 버튼 클릭 또는 ```F5``` 를 눌러서 debug 시작

<iframe width="560" height="315" src="//www.youtube.com/embed/YnkeDlf0IU4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



## 참고자료

-   [VS Code: Debugging Jest](https://gist.github.com/jherax/231b2dda7f9cce20e13f4590594fdb70)
