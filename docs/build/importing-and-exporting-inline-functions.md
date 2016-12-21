---
title: "인라인 함수 가져오기 및 내보내기 | Microsoft Docs"
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
  - "DLL[C++], 내보내기"
  - "DLL[C++], 가져오기"
  - "함수 내보내기[C++], 인라인 함수"
  - "함수[C++], 내보내기"
  - "함수[C++], 가져오기"
  - "함수 가져오기[C++]"
  - "인라인 함수 가져오기[C++]"
  - "인라인 함수[C++], 내보내기"
  - "인라인 함수[C++], 가져오기"
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 함수 가져오기 및 내보내기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

가져오는 함수를 인라인으로 정의할 수 있습니다.  그 효과는 표준 함수를 인라인으로 정의할 때와 거의 비슷하며, 이러한 함수 호출은 매크로와 마찬가지로 인라인 코드로 확장됩니다.  함수를 인라인으로 정의하면 효율성을 위해 멤버 함수 일부를 인라인할 수 있는 DLL의 C\+\+ 클래스를 지원하는 데 매우 유용합니다.  
  
 가져오는 인라인 함수의 한 가지 특징은 사용자가 함수의 주소를 C\+\+ 형식으로 가져올 수 있다는 점입니다.  컴파일러는 DLL에 상주하는 인라인 함수의 복사본 주소를 반환합니다.  가져오는 인라인 함수의 또 다른 특징은 가져오는 전역 데이터와 달리 가져오는 함수의 정적 지역 데이터를 초기화할 수 있다는 점입니다.  
  
> [!CAUTION]
>  가져온 인라인 함수를 제공할 때에는 버전 충돌이 일어날 수 있으므로 특별히 주의해야 합니다.  인라인 함수는 응용 프로그램 코드로 확장됩니다. 따라서 나중에 이 함수를 다시 쓰는 경우 해당 응용 프로그램을 다시 컴파일해야만 함수가 업데이트됩니다. 반면, 일반적인 DLL 함수는 해당 함수를 사용하는 응용 프로그램을 다시 빌드하지 않아도 업데이트됩니다.  
  
## 수행할 작업  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
-   [.DEF 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS를 사용하여 내보내기 및 가져오기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C\+\+ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\)을 사용하여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
## 참고 항목  
 [가져오기 및 내보내기](../build/importing-and-exporting.md)