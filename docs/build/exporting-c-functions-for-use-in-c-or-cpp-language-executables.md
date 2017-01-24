---
title: "C 함수를 C 또는 C++ 언어 실행 파일에서 사용할 수 있도록 내보내기 | Microsoft Docs"
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
  - "__cplusplus 매크로"
  - "DLL 내보내기[C++], C++ 실행 파일의 C 함수"
  - "함수 내보내기[C++], C++ 실행 파일의 C 함수"
  - "함수[C++], C 또는 C++ 실행 파일"
  - "함수[C++], 내보내기"
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C 함수를 C 또는 C++ 언어 실행 파일에서 사용할 수 있도록 내보내기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL에 포함된 C로 작성된 함수를 C 언어 또는 C\+\+ 언어 모듈에서 액세스하려면 전처리기 매크로 **\_\_cplusplus**를 사용하여 컴파일될 언어를 결정한 다음, C\+\+ 언어 모듈에서 사용할 경우 이 함수를 C 링크로 선언해야 합니다.  이 방법을 사용하고 DLL에 헤더 파일을 제공하면 C 및 C\+\+ 사용자가 별도의 변경 없이도 이 함수를 사용할 수 있게 됩니다.  
  
 다음 코드는 C 및 C\+\+ 클라이언트 응용 프로그램에서 사용할 수 있는 헤더 파일을 보여 줍니다.  
  
```  
// MyCFuncs.h  
#ifdef __cplusplus  
extern "C" {  // only need to export C interface if  
              // used by C++ source code  
#endif  
  
__declspec( dllimport ) void MyCFunc();  
__declspec( dllimport ) void AnotherCFunc();  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
 C 함수를 C\+\+ 실행 파일에 링크해야 하는 경우 함수 선언 헤더 파일에서 위의 방법을 사용하지 않았으면 C\+\+ 소스 파일에 다음을 추가하여 컴파일러에서 C 함수 이름을 데코레이팅하지 않게 합니다.  
  
```  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## 수행할 작업  
  
-   [.def 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS를 사용하여 내보내기 및 가져오기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\)을 사용하여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 추가 정보  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
-   [링크 사양](http://msdn.microsoft.com/ko-kr/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## 참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)