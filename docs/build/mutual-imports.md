---
title: "상호 가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- mutual DLL imports [C++]
- AFX_DATA
- importing DLLs [C++], mutual imports
- mutually importing executable files [C++]
- AFX_EXT_CLASS macro
- circular imports
- _AFXEXT preprocessor symbol
- DLLs [C++], importing
- executable files [C++], importing
- extension DLLs [C++], mutual imports
- exporting DLLs [C++], mutual imports
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfd31cd4e5776555137daf002c076e14d4031f89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mutual-imports"></a>상호 가져오기
Import에는 상호 (또는 순환) 내보내기 또는 가져오기를 다른 실행 파일에 대해 복잡해 집니다. 예를 들어 두 개의 Dll 상호 재귀 함수를 유사한 다른 기호를 가져옵니다.  
  
 다른 첫 번째 작성 하지 않고 작성할 수 있는지 둘 다는 실행 파일 (대개 Dll) 상호 가져오기 문제가 발생 합니다. 각 빌드 프로세스의 다른 빌드 프로세스에서 생성 된 가져오기 라이브러리를 입력으로 필요 합니다.  
  
 솔루션은 LIB 유틸리티를 실행 파일을 작성 하지 않고 가져오기 라이브러리를 생성 하는 /DEF 옵션을 사용 하는 것입니다. 이 유틸리티를 사용 하 여 필요한 모든 가져오기 라이브러리를 빌드할 수 관련 된 Dll에 관계 없이 또는 복잡 한 정도 종속성의 합니다.  
  
 상호 가져오기를 처리 하기 위한 일반적인 해결책은입니다.  
  
1.  차례로 각 DLL을 가져옵니다. (일부 순서는 적합 하지만 순서에 관계 없이 불가능.) 모든 필요한 가져오기 라이브러리가 존재 하 고 최신인 실행 파일 (DLL)를 작성 하는 링크를 실행 합니다. 가져오기 라이브러리를 생성 합니다. LIB 가져오기 라이브러리를 생성, 실행 합니다.  
  
     /DEF 옵션으로 LIB 실행에서 추가 파일을 생성 합니다.는 합니다. EXP 확장입니다. 합니다. EXP 파일을 실행 파일을 빌드합니다 나중에 사용 해야 합니다.  
  
2.  링크 또는 LIB를 사용 하 여 모든 가져오기 라이브러리를 빌드를 뒤로 돌아가서 링크 실행 파일을 이전 단계에서 빌드되지 않은 빌드를 실행 합니다. 참고 링크 줄에 해당.exp 파일을 지정 해야 합니다.  
  
     가져오기 라이브러리 DLL1을 생성 하 고 이전 LIB 유틸리티를 실행 하는 경우 생성 되어 있을 것은 dll1.exp 합니다. DLL1.exp DLL1.dlll 빌드할 때 링크에 대 한 입력으로 사용 해야 합니다.  
  
 다음 그림에서는 두 개의 상호 가져오기 Dll, DLL1 및 d l l 2에 대 한 솔루션을 보여 줍니다. 1 단계 /DEF 옵션 집합을 DLL1 LIB를 실행 하는 것입니다. 1 단계 DLL1.lib, 한 가져오기 라이브러리 및 DLL1.exp를 생성합니다. 2 단계에서는 가져오기 라이브러리를 사용 하 여 빌드하려면 d l l 2, d l l 2의 기호에 대 한 가져오기 라이브러리를 생성 합니다. 3 단계 DLL1.exp 및 DLL2.lib 입력으로 사용 하 여 DLL1를 작성 합니다. LIB d l l 2의 가져오기 라이브러리를 빌드를 사용 하지 않았으므로 d l l 2에 대 한.exp 파일 필요한 아닌지 확인 합니다.  
  
 ![상호 가져오기를 사용 하 여 두 개의 Dll 연결](../build/media/vc37yj1.gif "vc37YJ1")  
상호 가져오기를 사용하여 두 개의 DLL 연결  
  
## <a name="limitations-of-afxext"></a>_AFXEXT의 제한 사항  
 사용할 수는 `_AFXEXT` MFC 확장 Dll 오지 않아도 MFC 확장 Dll의 여러 계층에 전처리기 기호입니다. MFC 확장 호출 또는 사용자의 MFC 확장 Dll MFC 클래스에서 다음 파생 되는 클래스에서 파생 되는 Dll이 있는 경우에 모호성을 피하기 위해 사용자 고유의 전처리기 기호를 사용 해야 합니다.  
  
 이 문제는 해당에 Win32, 모든 데이터를 명시적으로 선언 해야 **__declspec (dllexport)** DLL에서 가져와야 하는 경우 및 **__declspec (dllimport)** DLL에서 가져와야 하는 경우. 정의 하는 경우 `_AFXEXT`, MFC 헤더 되도록 **AFX_EXT_CLASS** 제대로 정의 됩니다.  
  
 있는 경우 여러 개의 레이어, 하나의 기호와 같은 **AFX_EXT_CLASS** MFC 확장 DLL이 다른 MFC 확장 DLL에서에서 다른 클래스를 가져올 뿐만 아니라 새 클래스를 내보낼 수 있으므로 충분 하지 않습니다. 이 문제를 해결 하기 위해 작성할 수 있도록 DLL 자체 DLL을 사용 하 여 비교를 나타내는 특수 전처리기 기호를 사용 합니다. 예를 들어 두 개의 MFC 확장 Dll, A.dll 및 B.dll 한다고 가정 합니다. 구성 파일은 각각의 일부 클래스 A.h와 B.h에 각각 내보냅니다. B.dll은 A.dll에서 클래스를 사용 합니다. 헤더 파일 모양은 다음과 같습니다.  
  
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
  
 사용 하 여 빌드 A.dll를 빌드할 때 `/D A_IMPL` 사용 하 여 빌드 B.dll를 빌드할 때 및 `/D B_IMPL`합니다. 각 DLL에 대 한 별도 기호를 사용 하 여 `CExampleB` 내보낸 및 `CExampleA` B.dll를 빌드할 때 가져온 합니다. `CExampleA`A.dll 빌드될 때 이며 B.dll (또는 다른 클라이언트)가 사용 될 때 가져오게 됩니다.  
  
 기본 제공을 사용 하는 경우 이러한 유형의 쌓기를 수행할 수 없는 **AFX_EXT_CLASS** 및 `_AFXEXT` 전처리기 기호입니다. 위에서 설명한 기술을 액티브 기술, 데이터베이스 및 네트워크 MFC 확장 Dll을 빌드할 때 메커니즘은 MFC를 직접 사용 하 여 방식으로이 문제를 해결 합니다.  
  
## <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않는 경우  
 전체 클래스를 내보내지 않는 경우에 MFC 매크로에서 만든 필요한 데이터 항목 내보내집니다 확인 해야 합니다. 다시 정의 하 여이 작업을 수행할 수 있습니다 `AFX_DATA` 특정 클래스의 매크로를 합니다. 이렇게 해야 전체 클래스를 내보내지 않는 언제 든 지 합니다.  
  
 예:  
  
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
  
### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
-   [사용 하 여 DLL에서 내보냅니다. DEF 파일](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec (dllexport)를 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS를 사용 하 여 가져오기 및 내보내기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 언어 실행 파일에서 사용 하기 위해 c + + 함수 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec (dllimport)을 사용 하 여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
### <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [LIB 유틸리티 및 /DEF 옵션](../build/reference/lib-reference.md)  
  
## <a name="see-also"></a>참고 항목  
 [가져오기 및 내보내기](../build/importing-and-exporting.md)