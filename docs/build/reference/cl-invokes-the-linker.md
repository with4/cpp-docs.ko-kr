---
title: "CL에서의 링커 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러[C++], 링크하지 않고 컴파일"
  - "cl.exe 컴파일러[C++], 링커 제어"
  - "소스 코드 컴파일[C++], 링크하지 않고 컴파일"
  - "컴파일러에서 링커 호출"
  - "LINK 도구[C++], CL 컴파일러에서 호출"
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CL에서의 링커 호출
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL은 \/c 옵션이 설정되어 있지 않으면 컴파일한 다음 자동으로 링커를 호출합니다.  CL은 컴파일하는 동안 만들어진 .obj 파일의 이름과 명령줄에서 지정한 다른 모든 파일의 이름을 링커에 전달합니다.  링커는 LINK 환경 변수에 나열된 옵션을 사용합니다.  \/link 옵션을 사용하면 CL 명령줄에서 링커 옵션을 지정할 수 있습니다.  \/link 옵션 뒤에 있는 옵션은 LINK 환경 변수에 지정된 옵션을 무시합니다.  다음 표에서는 링크 과정을 생략하도록 만드는 옵션을 보여 줍니다.  
  
|옵션|설명|  
|--------|--------|  
|\/c|링크하지 않고 컴파일합니다.|  
|\/E, \/EP, \/P|컴파일이나 링크하지 않고 전처리만 합니다.|  
|\/Zg|함수 프로토타입을 생성합니다.|  
|\/Zs|구문을 검사합니다.|  
  
 링크 작업에 대한 자세한 내용은 [링커 옵션](../../build/reference/linker-options.md)을 참조하십시오.  
  
## 예제  
 다른 파일 내에 정의된 함수를 호출하는 MAIN.c, MOD1.c 및 MOD2.c와 같은 세 개의 C 소스 파일을  컴파일한다고 가정합니다.  
  
-   MAIN.c는 MOD1.c에 있는 함수 `func1`을 호출하고 MOD2.c에 있는 함수 `func2`를 호출합니다.  
  
-   MOD1.c은 표준 라이브러리 함수인 `printf_s`와 `scanf_s`를 호출합니다.  
  
-   MOD2.c는 `myline`과 `mycircle`이라는 그래픽 함수를 호출합니다. 이 그래픽 함수는 MYGRAPH.lib라는 라이브러리에 정의되어 있습니다.  
  
 이러한 프로그램을 빌드하려면 다음 명령줄을 사용하여 컴파일합니다.  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 CL은 세 개의 C 소스 파일을 먼저 컴파일한 후 MAIN.obj, MOD1.obj 및 MOD2.obj 목적 파일을 만듭니다.  컴파일러는 표준 라이브러리의 이름을 각 .obj 파일에 지정합니다.  자세한 내용은 [런타임 라이브러리 사용](../../build/reference/md-mt-ld-use-run-time-library.md)을 참조하십시오.  
  
 CL은 .obj 파일의 이름과 MYGRAPH.lib 이름을 링커에 전달합니다.  링커는 외부 참조를 다음과 같이 해결합니다.  
  
1.  MAIN.obj에서 `func1`에 대한 참조는 MOD1.obj의 정의를 사용하여 확인하고 `func2`에 대한 참조는 MOD2.obj의 정의를 사용하여 확인합니다.  
  
2.  MOD1.obj에서 `printf_s`와 `scanf_s`에 대한 참조는 MOD1.obj에 지정된 이름을 통해 링커에서 찾은 라이브러리의 정의를 사용하여 해결합니다.  
  
3.  MOD2.obj에서 `myline`과 `mycircle`에 대한 참조는 MYGRAPH.lib의 정의를 사용하여 확인합니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)