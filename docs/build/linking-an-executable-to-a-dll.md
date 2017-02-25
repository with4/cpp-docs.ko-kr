---
title: "DLL에 실행 파일 링크 | Microsoft Docs"
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
  - "DLL[C++], 링크"
  - "동적 로드 링크[C++]"
  - "실행 파일[C++], DLL에 연결"
  - "명시적 링크[C++]"
  - "암시적 링크[C++]"
  - "링크[C++], DLL"
  - "DLL 로드[C++]"
  - "런타임[C++], 링크"
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# DLL에 실행 파일 링크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

실행 파일은 다음의 두 가지 방법 중 하나를 사용하여 DLL에 링크하거나 DLL을 로드합니다.  
  
-   [암시적 링크](../build/linking-implicitly.md)  
  
-   [명시적 링크](../build/linking-explicitly.md)  
  
 암시적 링크는 정적 로드 또는 로드타임 동적 링크라고도 합니다.  반면, 명시적 링크는 동적 로드 또는 런타임 동적 링크라고도 합니다.  
  
 암시적 링크의 경우, DLL을 사용하는 실행 파일은 DLL 작성자가 제공하는 가져오기 라이브러리\(.lib 파일\)에 링크합니다.  DLL을 사용하는 실행 파일이 로드될 때 운영 체제에서 해당 DLL을 로드합니다.  클라이언트 실행 파일에서는 해당 실행 파일 내에 들어 있는 함수를 호출할 때와 마찬가지로 DLL의 내보내기 함수를 호출합니다.  
  
 명시적 링크의 경우, DLL을 사용하는 실행 파일이 함수를 호출하여 DLL을 명시적으로 로드 및 언로드하고 DLL의 내보내기 함수에 액세스해야 합니다.  클라이언트 실행 파일은 함수 포인터를 통해 이 내보내기 함수를 호출해야 합니다.  
  
 실행 파일은 두 링크 방법 모두에서 동일한 DLL을 사용할 수 있습니다.  또한 이 메커니즘들은 함께 사용될 수 있어 하나의 실행 파일이 DLL에 암시적으로 링크하고 다른 실행 파일은 그 DLL에 명시적으로 링크할 수 있습니다.  
  
## 추가 정보  
  
-   [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)  
  
-   [Windows에서 DLL을 찾는 데 사용되는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)