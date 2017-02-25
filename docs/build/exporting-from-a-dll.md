---
title: "DLL에서 내보내기 | Microsoft Docs"
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
  - "DLL 내보내기[C++]"
  - "DLL[C++], 내보내기"
  - "DLL 내보내기[C++]"
  - "DLL 내보내기[C++], DLL에서 내보내기 정보"
  - "함수 내보내기[C++], DLL(가져오기)"
  - "내보내기 테이블[C++]"
  - "함수[C++], 내보내기"
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# DLL에서 내보내기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL 파일의 레이아웃은 DLL 파일의 경우 내보내기 테이블이 포함된다는 중요한 차이점만 제외하고는 .exe 파일의 레이아웃과 매우 유사합니다.  내보내기 테이블에는 해당 DLL이 다른 실행 파일에 내보내는 모든 함수의 이름이 들어 있습니다.  이 함수는 DLL로의 진입점이며, 다른 실행 파일은 이 내보내기 테이블에 있는 함수만 액세스할 수 있습니다.  DLL에 있는 다른 함수들은 해당 DLL의 전용 함수입니다.  [DUMPBIN](../build/reference/dumpbin-reference.md) 도구와 \/EXPORTS 옵션을 함께 사용하면 DLL의 내보내기 테이블을 볼 수 있습니다.  
  
 다음과 같은 두 가지 방법을 사용하여 DLL에서 함수를 내보낼 수 있습니다.  
  
-   모듈 정의 파일\(.def\)을 만들어 DLL 빌드 시 이 .def 파일을 사용.  [이름 대신 서수를 사용하여 DLL에서 함수를 내보내려는 경우](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) 이 방법을 사용합니다.  
  
-   함수 정의에 **\_\_declspec\(dllexport\)** 키워드 사용  
  
 위의 방법으로 함수를 내보낼 때에는 [\_\_stdcall](../cpp/stdcall.md) 호출 규칙을 사용해야 합니다.  
  
## 수행할 작업  
  
-   [.def 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS를 사용하여 내보내기 및 가져오기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C\+\+ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C 함수를 C 또는 C\+\+ 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [이름 대신 서수를 사용하여 DLL에서 함수 내보내기](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 추가 정보  
  
-   [응용 프로그램으로 가져오기](../build/importing-into-an-application.md)  
  
-   [인라인 함수 가져오기 및 내보내기](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
## 참고 항목  
 [가져오기 및 내보내기](../build/importing-and-exporting.md)