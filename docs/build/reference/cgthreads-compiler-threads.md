---
title: "/CGTHREADS(컴파일러 스레드) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CGTHREADS 링커 옵션"
  - "CGTHREADS 링커 옵션"
  - "-CGTHREADS 링커 옵션"
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /CGTHREADS(컴파일러 스레드)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링크 타임 코드 생성이 지정된 경우 최적화 및 코드 생성에 사용할 cl.exe 스레드의 수를 설정합니다.  
  
## 구문  
  
```  
/CGTHREADS:[1-8]  
```  
  
## 인수  
 number  
 사용할 cl.exe to의 최대 스레드 수\(범위 1~8\)  
  
## 설명  
 **\/CGTHREADS** 옵션은 링크 타임 코드 생성\([\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)\)이 지정되면 cl.exe에서 컴파일의 최적화 및 코드 생성 구에 사용할 최대 스레드 수를 지정합니다.  기본적으로 cl.exe에서는 **\/CGTHREADS:4**가 지정된 것처럼 스레드 4개를 사용합니다.  더 많은 프로세서 코어를 사용할 수 있는 경우에는 더 큰 `number` 값으로 인해 빌드 시간이 줄어들 수 있습니다.  
  
 빌드에 여러 수준의 병렬 처리를 지정할 수 있습니다.  msbuild.exe 스위치인 **\/maxcpucount**는 병렬로 실행할 수 있는 MSBuild 프로세스의 수를 지정합니다.  [\/MP\(여러 프로세스로 빌드\)](../../build/reference/mp-build-with-multiple-processes.md) 컴파일러 플래그는 소스 파일을 동시에 컴파일하는 cl.exe 프로세스의 수를 지정합니다.  [\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md) 컴파일러 옵션은 각 cl.exe 프로세스에서 사용하는 스레드 수를 지정합니다.  프로세서는 프로세서 코어와 동일한 수의 스레드를 동시에 실행할 수 있으므로 이러한 모든 옵션에 대해 동시에 더 큰 값을 지정하는 것은 유용하지 않으며 오히려 역효과가 일어날 수 있습니다.  프로젝트를 병렬로 빌드하는 방법에 대한 자세한 내용은 [병렬로 여러 프로젝트 빌드](../Topic/Building%20Multiple%20Projects%20in%20Parallel%20with%20MSBuild.md)를 참조하세요.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **구성 속성**, **링커** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **\/CGTHREADS:** `number`를 포함하도록 **추가 옵션** 속성을 수정합니다. 여기서 `number`는 1~8 사이의 값입니다. 그런 다음 **확인**을 선택합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션](../../build/reference/linker-options.md)   
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)