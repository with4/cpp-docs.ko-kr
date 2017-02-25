---
title: "DEF 파일을 사용하여 DLL에서 내보내기 | Microsoft Docs"
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
  - ".def 파일[C++], DLL에서 내보내기"
  - "def 파일[C++], DLL에서 내보내기"
  - "DLL 내보내기[C++], DEF 파일"
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# DEF 파일을 사용하여 DLL에서 내보내기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모듈 정의\(.def\) 파일은 DLL의 여러 가지 특성을 설명하는 하나 이상의 모듈 문이 들어 있는 텍스트 파일입니다.  **\_\_declspec\(dllexport\)** 키워드를 사용하여 DLL의 함수를 내보내지 않는 경우에는 해당 DLL에 대한 .def 파일이 있어야 합니다.  
  
 .def 파일에는 적어도 다음과 같은 모듈 정의 문이 포함되어야 합니다.  
  
-   파일의 첫째 문은 LIBRARY 문이어야 합니다.  이 문은 해당 .def 파일이 DLL에 속한다는 것을 나타냅니다.  LIBRARY 문 다음에는 DLL의 이름이 옵니다.  링커는 이 이름을 DLL의 가져오기 라이브러리에 포함시킵니다.  
  
-   EXPORTS 문은 해당 DLL이 내보내기 함수의 이름 및 서수 값\(선택적\)을 나열합니다.  함수 이름 다음에 @ 기호와 숫자를 사용하여 해당 함수에 서수 값을 할당합니다.  서수 값을 지정할 때 사용할 수 있는 서수 값의 범위는 1부터 N까지이며, 여기에서 N은 해당 DLL에서 내보내기 함수의 수입니다.  서수 순서로 함수를 내보내려면 [이름 대신 서수를 사용하여 DLL에서 함수 내보내기](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)도 참조하십시오.  
  
 예를 들어, 이진 검색 트리를 구현하는 코드가 들어 있는 DLL의 형식은 다음과 같습니다.  
  
```  
LIBRARY   BTREE  
EXPORTS  
   Insert   @1  
   Delete   @2  
   Member   @3  
   Min   @4  
```  
  
 [MFC DLL 마법사](../mfc/reference/mfc-dll-wizard.md)를 사용하여 MFC DLL을 만드는 경우에는 마법사가 사용자 대신 기초 .def 파일을 만들고 이 파일을 프로젝트에 자동으로 추가합니다.  그러면 내보내기 함수의 이름을 이 파일에 추가합니다.  비 MFC DLL의 경우에는 사용자가 직접 .def 파일을 만들어 프로젝트에 추가해야 합니다.  
  
 C\+\+ 파일에서 함수를 내보내는 경우에는 .def 파일에 데코레이팅된 이름을 포함시키거나 extern "C"를 사용하여 내보내기 함수를 표준 C 링크로 정의해야 합니다.  .def 파일에 데코레이팅된 이름을 포함해야 하는 경우 이 이름은 [DUMPBIN](../build/reference/dumpbin-reference.md) 도구 또는 링커 옵션 [\/MAP](../build/reference/map-generate-mapfile.md)을 사용하여 가져올 수 있습니다.  컴파일러에서 생성된 데코레이팅된 이름은 해당 컴파일러에서만 사용할 수 있습니다.  Visual C\+\+ 컴파일러에서 생성된 데코레이팅된 이름을 .def 파일에 포함하는 경우, 호출 응용 프로그램의 데코레이팅된 이름과 DLL의 .def 파일에 있는 내보내는 이름이 일치하도록 해당 DLL에 링크하는 응용 프로그램도 같은 버전의 Visual C\+\+를 사용하여 빌드해야 합니다.  
  
 [확장 DLL](../build/extension-dlls-overview.md)을 빌드하고 .def 파일을 사용하여 내보내는 경우에는 내보내는 클래스가 들어 있는 헤더 파일의 처음과 끝 부분에 다음 코드를 추가합니다.  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 이 코드 줄을 추가하면 내부적으로 사용되거나 클래스에 추가되는 MFC 변수를 해당 확장 DLL에서 내보내거나 가져올 수 있습니다.  예를 들어, `DECLARE_DYNAMIC`을 사용하여 클래스를 파생시키는 경우에는 이 매크로가 확장되어 클래스에 `CRuntimeClass` 멤버 변수를 추가합니다.  이 네 줄의 코드가 없으면 DLL이 올바르게 컴파일 또는 링크되지 않거나 클라이언트 응용 프로그램이 DLL에 링크할 때 오류가 발생할 수 있습니다.  
  
 DLL 빌드 시 링커는 .def 파일을 사용하여 내보내기 파일\(.exp\) 및 가져오기 라이브러리 파일\(.lib\)을 만듭니다.  그런 다음 링커는 이 내보내기 파일을 사용하여 DLL 파일을 빌드합니다.  또한 해당 DLL을 암시적으로 링크하는 실행 파일은 빌드 시 가져오기 라이브러리에 링크합니다.  
  
 MFC 자체는 .def 파일을 사용하여 함수 및 클래스를 MFCx0.dll에서 내보냅니다.  
  
## 수행할 작업  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS를 사용하여 내보내기 및 가져오기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C\+\+ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C 함수를 C 또는 C\+\+ 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\)을 사용하여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 추가 정보  
  
-   [.def 파일](../build/reference/module-definition-dot-def-files.md)  
  
-   [모듈 정의 문의 규칙](../build/reference/rules-for-module-definition-statements.md)  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
-   [인라인 함수 가져오기 및 내보내기](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
## 참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)