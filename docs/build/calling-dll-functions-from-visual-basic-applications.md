---
title: "Visual Basic 응용 프로그램에서 DLL 함수 호출 | Microsoft Docs"
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
  - "__stdcall 키워드[C++]"
  - "VB 응용 프로그램에서 DLL 함수 호출[C++]"
  - "DLL 함수[C++]"
  - "DLL 함수[C++], 호출"
  - "DLL[C++], 호출"
  - "함수 호출[C++], DLL 함수"
  - "함수[C++], Visual Basic에서 DLL 함수 호출"
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual Basic 응용 프로그램에서 DLL 함수 호출
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Basic 응용 프로그램 또는 파스칼이나 포트란 등의 다른 언어로 된 응용 프로그램에서 C\/C\+\+ DLL에 있는 함수를 호출하려면 컴파일러에 의한 이름 데코레이션 없이 올바른 호출 규칙을 사용하여 해당 함수를 내보내야 합니다.  
  
 `__stdcall`은 함수에 대해 올바른 호출 규칙\(호출되는 함수는 스택을 정리하고 매개 변수는 오른쪽에서 왼쪽으로 전달됨\)을 만들지만 함수 이름을 다르게 데코레이팅합니다.  따라서 DLL의 내보내기 함수에 대해 **\_\_declspec\(dllexport\)**을 사용하면 데코레이팅된 이름이 내보내집니다.  
  
 `__stdcall` 이름 데코레이션은 기호 이름에 밑줄\(\_\)을 접두사로 붙인 다음, 이 기호에 @ 문자와 인수 목록의 바이트 수\(필요한 스택 공간\)를 차례로 추가합니다.  예를 들어, 다음과 같이 선언된 함수가 있습니다.  
  
```  
int __stdcall func (int a, double b)  
```  
  
 이 함수는 다음과 같이 데코레이팅됩니다.  
  
```  
_func@12  
```  
  
 C 호출 규칙\(`__cdecl`\)은 함수 이름을 `_func`로 데코레이팅합니다.  
  
 데코레이팅된 이름을 가져오려면 [\/MAP](../build/reference/map-generate-mapfile.md)을 사용합니다.  **\_\_declspec\(dllexport\)**의 사용 방법은 다음과 같습니다.  
  
-   C 호출 규칙\(**\_cdecl**\)을 사용하여 함수를 내보내는 경우 함수 이름을 내보낼 때 앞에 있는 밑줄\(\_\)을 제거합니다.  
  
-   내보내기 함수가 C 호출 규칙이 아닌 다른 규칙\(예: `__stdcall`\)을 사용하는 경우 데코레이팅된 이름을 내보냅니다.  
  
 스택 정리가 발생하는 위치는 재정의할 수 없으므로 `__stdcall`을 사용해야 합니다.  `__stdcall`을 사용하여 데코레이팅된 이름을 해제하려면 .def 파일의 EXPORTS 섹션에 있는 별칭을 사용하여 이름을 지정해야 합니다.  다음 함수 선언에 대한 이름 지정 방법은 아래에 설명되어 있습니다.  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 .DEF 파일의 내용은 다음과 같습니다.  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 Visual Basic으로 만든 프로그램에서 DLL을 호출하려면 .def 파일에서 이 항목에 설명된 별칭 방법을 사용해야 합니다.  해당 별칭이 Visual Basic 프로그램에서 만들어진 것이면 .def 파일에서 별칭을 사용할 필요가 없습니다.  [Declare](../Topic/Declare%20Statement.md) 문에 alias 절을 추가하면 Visual Basic 프로그램에서 이 작업을 자동으로 수행할 수 있습니다.  
  
## 추가 정보  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
-   [.def 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C\+\+ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)