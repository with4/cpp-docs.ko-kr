---
title: "링커 도구 경고 LNK4210 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4210"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4210"
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4210
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

section 섹션이 있습니다. 처리되지 않은 정적 이니셜라이저 또는 종결자가 있을 수 있습니다.  
  
 일부 코드가 정적 이니셜라이저 또는 종결자를 파생시켰지만 응용 프로그램이 시작될 때 이니셜라이저나 종결자를 실행해야 하는 CRT 또는 동등 항목이 실행되지 않았습니다.  이 오류를 발생시키는 코드의 예입니다.  
  
-   생성자, 소멸자 또는 가상 함수 테이블이 있는 전역 클래스 변수  
  
-   비 컴파일 타임 상수로 초기화된 전역 변수  
  
 이 문제를 해결하려면 다음 중 하나를 수행하십시오.  
  
-   정적 이니셜라이저를 포함하는 코드를 모두 제거합니다.  
  
-   [\/NOENTRY](../../build/reference/noentry-no-entry-point.md)를 사용하지 마십시오.  \/NOENTRY를 제거한 다음 msvcrt.lib, libcmt.lib 또는 libcmtd.lib를 링커 명령줄에 추가해야 할 수도 있습니다.  
  
-   msvcrt.lib, libcmt.lib 또는 libcmtd.lib를 링커 명령줄에 추가합니다.  
  
-   \/clr:pure 컴파일에서 \/clr로 바꿀 때는 링커 라인에서 [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) 옵션을 제거합니다.  이렇게 하면 CRT 초기화가 사용되므로 응용 프로그램 시작 시 정적 이니셜라이저가 실행됩니다.  
  
-   [\/ENTRY](../../build/reference/entry-entry-point-symbol.md)를 사용하여 빌드한 프로젝트에서 \/ENTRY를 `_DllMainCRTStartup`이 아닌 다른 함수에 전달하는 경우 이 함수가 CRT\_INIT를 호출해야 합니다.  [런타임 라이브러리 동작](../../build/run-time-library-behavior.md) 및 기술 자료 문서 Q94248, [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;94248](http://support.microsoft.com/default.aspx?scid=kb;en-us;94248) 에 대한 자세한 내용을 위해 확인하세요.  
  
 [\/GS](../../build/reference/gs-buffer-security-check.md) 컴파일러 옵션에는 CRT 시작 코드가 필요합니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)