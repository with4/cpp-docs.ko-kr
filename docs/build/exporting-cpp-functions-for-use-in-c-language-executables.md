---
title: "C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL 내보내기[C++], C 실행 파일의 C++ 함수"
  - "함수 내보내기[C++], C 실행 파일의 C++ 함수"
  - "함수[C++], C 실행 파일의 C++ 함수"
  - "함수[C++], 내보내기"
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL에 포함된 C\+\+로 작성된 함수를 C 언어 모듈에서 액세스하려는 경우에는 C\+\+ 링크 대신 C 링크를 사용하여 해당 함수를 선언해야 합니다.  별도로 지정되지 않은 경우, C\+\+ 컴파일러는 C에서는 호출하기 어려울 수 있는 C\+\+의 형식 안전 명명 규칙\(이름 데코레이션이라고도 함\)과 호출 규칙을 사용합니다.  
  
 C 링크를 지정하려면 함수 선언에 대해 **extern** "**C**"를 지정합니다.  예를 들면 다음과 같습니다.  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## 수행할 작업  
  
-   [.def 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS를 사용하여 내보내기 및 가져오기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 함수를 C 또는 C\+\+ 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\)을 사용하여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 추가 정보  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
-   [링크 사양](http://msdn.microsoft.com/ko-kr/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## 참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)