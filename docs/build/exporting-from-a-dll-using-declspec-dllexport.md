---
title: "__declspec(dllexport)을 사용하여 DLL에서 내보내기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dllexport"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllexport) 키워드[C++]"
  - "내보내기 지시문[C++]"
  - "DLL 내보내기[C++], __declspec(dllexport) 키워드"
  - "이름[C++], DLL 내보내기"
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __declspec(dllexport)을 사용하여 DLL에서 내보내기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft에서는 16비트 컴파일러 버전의 Visual C\+\+에 **\_\_export**를 도입하여 컴파일러에서 내보내기 이름을 자동으로 생성한 다음 .lib 파일에 포함시킬 수 있도록 하였습니다.  이 .lib 파일은 DLL에 링크하는 정적 .lib와 마찬가지로 사용할 수 있습니다.  
  
 새 컴파일러 버전에서는 **\_\_declspec\(dllexport\)** 키워드를 사용하여 DLL에서 데이터, 함수, 클래스 또는 클래스 멤버 함수를 내보낼 수 있습니다.  **\_\_declspec\(dllexport\)**은 개체 파일에 내보내기 지시문을 추가하므로 .def 파일을 사용할 필요가 없습니다.  
  
 이는 C\+\+ 함수의 데코레이팅된 이름을 내보내려고 할 때 특히 편리합니다.  이름 데코레이션에는 표준 사양이 없으므로 내보내기 함수의 이름은 컴파일러 버전 간에 변경될 수 있습니다.  **\_\_declspec\(dllexport\)**을 사용하는 경우에는 이름 규칙의 변경 사항이 있을 때만 해당 DLL 및 종속된 .exe 파일을 다시 컴파일합니다.  
  
 서수, NONAME 및 PRIVATE 등의 많은 내보내기 지시문은 .def 파일에서만 만들 수 있으며 .def 파일을 사용하지 않고는 이러한 특성을 지정할 수 없습니다.  그러나 .def 파일과 **\_\_declspec\(dllexport\)**을 함께 사용하면 빌드 오류가 발생하지 않습니다.  
  
 키워드가 지정된 경우 함수를 내보내려면 **\_\_declspec\(dllexport\)** 키워드는 해당 호출 규칙 키워드의 왼쪽에 나타나야 합니다.  예를 들면 다음과 같습니다.  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 한 클래스의 공용 데이터 멤버 및 멤버 함수를 모두 내보내려면 이 키워드는 다음과 같이 해당 클래스 이름의 왼쪽에 나타나야 합니다.  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)`는 `__clrcall` 호출 규칙을 사용하여 함수에 적용할 수 없습니다.  
  
 일반적으로 DLL을 빌드할 때에는 내보내기 함수 프로토타입 및\/또는 클래스가 들어 있는 헤더 파일을 만들고 이 헤더 파일의 선언에 **\_\_declspec\(dllexport\)**을 추가합니다.  또한 코드를 읽기 쉽게 만들려면 다음과 같이 **\_\_declspec\(dllexport\)**에 대한 매크로를 정의한 다음 내보내는 각 기호에 대해 이 매크로를 사용합니다.  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **\_\_declspec\(dllexport\)**은 DLL의 내보내기 테이블에 함수 이름을 저장합니다.  테이블 크기를 최적화하려면 [이름 대신 서수를 사용하여 DLL에서 함수 내보내기](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)를 참조하십시오.  
  
> [!NOTE]
>  DLL 소스 코드를 Win16에서 Win32로 이식하려면 **\_\_export**의 각 인스턴스를 **\_\_declspec\(dllexport\)**으로 바꿉니다.  
  
 참조용으로 Win32 Winbase.h 헤더 파일을 검색해보십시오.  이 파일에는 **\_\_declspec\(dllimport\)**의 사용 예제가 들어 있습니다.  
  
## 수행할 작업  
  
-   [.def 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [AFX\_EXT\_CLASS를 사용하여 내보내기 및 가져오기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C\+\+ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C 함수를 C 또는 C\+\+ 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\)을 사용하여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 추가 정보  
  
-   [\_\_declspec 키워드](../cpp/declspec.md)  
  
-   [인라인 함수 가져오기 및 내보내기](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
## 참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)