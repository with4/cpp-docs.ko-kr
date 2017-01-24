---
title: "가져오기 및 내보내기 | Microsoft Docs"
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
  - "__declspec(dllimport) 키워드[C++]"
  - "DLL[C++], 내보내기"
  - "DLL[C++], 가져오기"
  - "DLL 내보내기[C++]"
  - "importing DLL[C++]"
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 가져오기 및 내보내기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음과 같은 두 가지 방법을 사용하여 공용 기호를 응용 프로그램으로 가져오거나 함수를 DLL에서 내보낼 수 있습니다.  
  
-   DLL 빌드 시 모듈 정의\(.def\) 파일 사용  
  
-   기본 응용 프로그램의 함수 정의에 **\_\_declspec\(dllimport\)** 또는 **\_\_declspec\(dllexport\)** 키워드 사용  
  
## .def 파일 사용  
 모듈 정의\(.def\) 파일은 DLL의 여러 가지 특성을 설명하는 하나 이상의 모듈 문이 들어 있는 텍스트 파일입니다.  **\_\_declspec\(dllimport\)** 또는 **\_\_declspec\(dllexport\)**을 사용하여 DLL의 함수를 내보내지 않는 경우에는 해당 DLL에 대한 .def 파일이 있어야 합니다.  
  
 .def 파일을 사용하면 [응용 프로그램으로 가져오기](../build/importing-using-def-files.md) 또는 [DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)도 가능합니다.  
  
## \_\_declspec 사용  
 Visual C\+\+에서는 이전에 16비트 버전의 Visual C\+\+에서 사용되었던 **\_\_export** 키워드 대신 **\_\_declspec\(dllimport\)** 및 **\_\_declspec\(dllexport\)**을 사용합니다.  
  
 코드가 올바르게 컴파일되도록 하기 위해 **\_\_declspec\(dllimport\)**을 사용할 필요는 없지만 이렇게 하면 컴파일러가 보다 나은 코드를 생성할 수 있게 됩니다.  컴파일러에서 더 나은 코드를 생성할 수 있는 이유는 함수가 DLL에 존재하는지 여부를 알 수 있기 때문입니다. 따라서 컴파일러에서는 일반적으로 DLL 경계를 넘는 함수 호출에서 지정되는 간접 참조 수준을 생략하도록 코드를 생성할 수 있습니다.  그러나 DLL에 사용되는 변수를 가져오려면 **\_\_declspec\(dllimport\)**을 사용해야 합니다.  
  
 올바른 .def 파일의 EXPORTS 섹션에는 **\_\_declspec\(dllexport\)**이 필요하지 않습니다.  이 경우에는 .def 파일을 사용하지 않고도 .exe 또는 .dll 파일에서 함수를 쉽게 내보낼 수 있도록 하기 위해 **\_\_declspec\(dllexport\)**이 추가되어 있습니다.  
  
 Win32의 이식 가능한 실행 파일 형식은 가져오기를 수정하기 위한 페이지의 수를 최소화하도록 디자인되어 있습니다.  이렇게 하려면 Win32의 이식 가능한 실행 파일 형식은 프로그램에 대한 모든 가져오기 주소를 가져오기 주소 테이블이라는 하나의 장소에 보관합니다.  이렇게 하면 로더에서 가져오기에 액세스할 때 한 개 또는 두 개의 페이지만 수정하면 됩니다.  
  
## 수행할 작업  
  
-   [응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)