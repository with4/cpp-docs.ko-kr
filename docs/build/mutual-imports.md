---
title: "상호 가져오기 | Microsoft Docs"
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
  - "_AFXEXT 전처리기 기호"
  - "AFX_DATA"
  - "AFX_EXT_CLASS 매크로"
  - "순환 가져오기"
  - "DLL[C++], 가져오기"
  - "실행 파일[C++], 가져오기"
  - "DLL 내보내기[C++], 상호 가져오기"
  - "확장 DLL[C++], 상호 가져오기"
  - "importing DLL[C++], 상호 가져오기"
  - "상호 DLL 가져오기[C++]"
  - "실행 파일 상호 가져오기[C++]"
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 상호 가져오기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

가져오기가 상호 간에 즉 순환적으로 수행되는 경우에는 다른 실행 파일에 대해 내보내기 또는 가져오기를 수행하는 것이 복잡해집니다.  예를 들어 두 개의 DLL이 상호 재귀 함수와 비슷하게 상호 간에 기호를 가져올 수 있습니다.  
  
 실행 파일\(대개 DLL\)의 상호 가져오기와 관련된 문제는 다른 실행 파일이 먼저 빌드되지 않으면 어떤 실행 파일도 빌드되지 않는다는 것입니다.  즉, 각 빌드 과정에는 다른 빌드 과정에서 생성된 가져오기 라이브러리를 입력으로 사용해야 합니다.  
  
 이 문제에 대한 해결책은 LIB 유틸리티를 \/DEF 옵션과 함께 사용하여 실행 파일을 빌드하지 않고도 가져오기 라이브러리를 생성하는 것입니다.  이 유틸리티를 사용하면 관련된 DLL의 수 또는 종속성의 복잡도와 상관 없이 필요한 모든 가져오기 라이브러리를 빌드할 수 있습니다.  
  
 상호 가져오기를 처리하기 위한 일반적인 해결책은 다음과 같습니다.  
  
1.  각 DLL을 차례로 가져옵니다. 이 때 보다 적합한 순서가 있을 수는 있지만 어떤 순서든지 사용할 수 있습니다. 현재 필요한 모든 가져오기 라이브러리가 있으면 LINK를 실행하여 실행 파일\(DLL\)을 빌드합니다.  이렇게 하면 가져오기 라이브러리가 생성됩니다.  또는, LIB를 실행하여 가져오기 라이브러리를 생성합니다.  
  
     \/DEF 옵션을 사용하여 LIB를 실행하면 확장명이 .EXP인 추가 파일이 생성됩니다.  이 .EXP 파일은 나중에 해당 실행 파일을 빌드하는 데 사용해야 합니다.  
  
2.  LINK 또는 LIB 중 하나를 사용하여 가져오기 라이브러리를 모두 빌드한 다음에는 이전 단계로 돌아가 LINK를 실행하여 아직 빌드되지 않은 실행 파일을 빌드합니다.  LINK 줄에 해당 .exp 파일을 지정해야 합니다.  
  
     이전에 LIB 유틸리티를 실행하여 DLL1에 대한 가져오기 라이브러리를 생성한 적이 있는 경우에는 DLL1.exp도 이미 생성되어 있을 것입니다.  DLL1.dll을 빌드할 때에는 DLL1.exp를 LINK에 대한 입력으로 사용해야 합니다.  
  
 아래 그림에서는 두 개의 상호 가져오기 DLL인 DLL1과 DLL2에 대한 해결책을 보여 줍니다.  1단계는 DLL1에 대해 \/DEF 옵션을 설정하여 LIB를 실행하는 것입니다.  1단계에서는 DLL1.lib, 가져오기 라이브러리 및 DLL1.exp를 생성합니다.  2단계에서는 이 가져오기 라이브러리를 사용하여 DLL2를 빌드하고, DLL2의 기호에 대한 가져오기 라이브러리를 생성합니다.  3단계에서는 DLL1.exp 및 DLL2.lib를 입력으로 사용하여 DLL1을 빌드합니다.  DLL2의 가져오기 라이브러리를 빌드할 때에는 LIB가 사용되지 않았으므로 DLL2에 대한 .exp 파일은 필요하지 않습니다.  
  
 ![두 개의 DLL을 상호 가져오기로 링크](../build/media/vc37yj1.png "vc37YJ1")  
두 개의 DLL을 상호 가져오기로 링크  
  
## \_AFXEXT의 제한 사항  
 전처리기 기호 `_AFXEXT`는 여러 계층의 확장 DLL이 없는 경우에만 확장 DLL에 사용될 수 있습니다.  사용자의 확장 DLL에 있는 클래스에서 호출 또는 파생되고 MFC 클래스에서 파생되는 확장 DLL이 있는 경우에는 모호성을 피하기 위해 사용자 고유의 전처리기 기호를 사용해야 합니다.  
  
 Win32에서는 모든 데이터를 명시적으로 **\_\_declspec\(dllexport\)**\(DLL에서 내보내는 경우\) 및 **\_\_declspec\(dllimport\)**\(DLL에서 가져오는 경우\)으로 선언해야 합니다.  `_AFXEXT`를 정의할 때 MFC 헤더에서 **AFX\_EXT\_CLASS**가 올바르게 정의되는지 확인합니다.  
  
 여러 계층이 있는 경우에는 확장 DLL이 또 다른 확장 DLL에서 다른 클래스를 가져올 뿐만 아니라 새 클래스를 내보낼 수도 있으므로 **AFX\_EXT\_CLASS** 같은 하나의 기호만으로는 충분하지 않습니다.  이 문제를 해결하려면 사용자가 해당 DLL을 빌드 및 사용하고 있는지를 나타내는 특별한 전처리기 기호를 사용합니다.  예를 들어 A.dll과 B.dll이라는 두 개의 확장 DLL이 있는데,  이 두 개의 DLL은 각각 A.h와 B.h에서 일부 클래스를 내보내며  B.dll은 A.dll의 클래스를 사용한다고 가정할 경우,  헤더 파일은 다음과 같습니다.  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A   __declspec(dllexport)  
#else  
   #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
  
// B.H  
#ifdef B_IMPL  
   #define CLASS_DECL_B   __declspec(dllexport)  
#else  
   #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition ... };  
...  
```  
  
 A.dll의 경우 `/D A_IMPL`을 사용하여 빌드되며, B.dll의 경우 `/D B_IMPL`을 사용하여 빌드됩니다.  각 DLL에 대해 별도의 기호를 사용하면 B.dll이 빌드될 때 `CExampleB`는 내보내고 `CExampleA`는 가져오게 됩니다.  `CExampleA`는 A.dll이 빌드될 때 내보내고 B.dll 또는 다른 클라이언트에 의해 사용될 때 가져오게 됩니다.  
  
 내장 전처리기 기호인 **AFX\_EXT\_CLASS**와 `_AFXEXT`를 사용할 때에는 이러한 형식의 계층이 형성될 수 없습니다.  위에서 설명된 방법을 사용하면 MFC 자체가 액티브 기술, 데이터베이스 및 네트워크 확장 DLL을 빌드할 때 사용하는 메커니즘과 같은 방식으로 이 문제를 해결할 수 있습니다.  
  
## 전체 클래스를 내보내지 않는 경우  
 전체 클래스를 내보내지 않는 경우에는 MFC 매크로에서 만드는 필수 데이터 항목을 올바르게 내보낼 수 있도록 해야 합니다.  `AFX_DATA`를 특정 클래스의 매크로에 맞게 다시 정의하여 이를 수행할 수 있습니다.  전체 클래스를 내보내지 않는 경우에는 이 작업을 반드시 수행해야 합니다.  
  
 예를 들면 다음과 같습니다.  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A  _declspec(dllexport)  
#else  
   #define CLASS_DECL_A  _declspec(dllimport)  
#endif  
  
#undef  AFX_DATA  
#define AFX_DATA CLASS_DECL_A  
  
class CExampleA : public CObject  
{  
   DECLARE_DYNAMIC()  
   CLASS_DECL_A int SomeFunction();  
   //... class definition ...  
};  
  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### 수행할 작업  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
-   [.DEF 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS를 사용하여 내보내기 및 가져오기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C\+\+ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\)을 사용하여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
### 추가 정보  
  
-   [LIB 유틸리티 및 \/DEF 옵션](../build/reference/lib-reference.md)  
  
## 참고 항목  
 [가져오기 및 내보내기](../build/importing-and-exporting.md)