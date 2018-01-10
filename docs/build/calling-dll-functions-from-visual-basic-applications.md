---
title: "Visual Basic 응용 프로그램에서 DLL 함수 호출 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed99b0ebe41a8f1bc9684638fa74e18556dd51f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Visual Basic 응용 프로그램에서 DLL 함수 호출
Visual Basic 응용 프로그램 (또는 Pascal 또는 포트란 같은 다른 언어에서는 응용 프로그램) C/c + + DLL의 함수를 호출에 대 한 올바른 호출 규칙을 사용 하 여 컴파일러에 의해 이름 데코레이션 없이 함수를 내보낼 수 해야 합니다.  
  
 `__stdcall`함수에 대 한 올바른 호출 규칙을 만듭니다 (스택을 정리 하는 호출된 된 함수 및 매개 변수는 오른쪽에서 왼쪽으로 전달 됩니다) 있지만 함수 이름을 다르게 데코레이팅합니다. 그럴 경우 **__declspec (dllexport)** 사용 데코레이팅된 이름을 내보내는 DLL에서 내보낸된 함수에 있습니다.  
  
 `__stdcall` 이름 데코레이션 기호 이름에 밑줄 (_)을 추가 at 기호 (@) 문자와 인수 목록 (필요한 스택 공간)의 바이트 수입니다. 결과적으로로 선언 된 함수가:  
  
```  
int __stdcall func (int a, double b)  
```  
  
 로 데코 레이트 합니다.  
  
```  
_func@12  
```  
  
 C 호출 규칙 (`__cdecl`) 이름으로 데코레이팅합니다 `_func`합니다.  
  
 데코 레이트 된 이름을 사용 하십시오 [/맵](../build/reference/map-generate-mapfile.md)합니다. 사용 하 여 **__declspec (dllexport)** 다음 작업을 수행 합니다.  
  
-   함수 C 호출 규칙을 사용 하 여 내보낸 경우 (**_cdecl**), 이름을 내보낼 때 선행 밑줄 (_)을 제거 합니다.  
  
-   내보내기 함수가 C 호출 규칙을 사용 하지 않는 경우 (예를 들어 `__stdcall`), 데코레이팅된 이름을 내보냅니다.  
  
 스택 정리의 발생 위치를 재정의할 수 없으므로 이기 때문에 사용 해야 `__stdcall`합니다. 레이트 된 이름을 해제 하려면 `__stdcall`,.def 파일의 EXPORTS 섹션에서 별칭을 사용 하 여 지정 해야 합니다. 이 작업은 다음 함수 선언에 대 한 다음과 같이 표시 됩니다.  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 안에. DEF 파일:  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 Visual Basic로 작성 된 프로그램에 의해 호출 되는 Dll,이 항목에 표시 하는 별칭 방법.def 파일에 필요 합니다. 별칭은 Visual Basic 프로그램에서 완료 되 면.def 파일의 별칭을 사용 하 여 필요 하지 않습니다. Alias 절을 추가 하 여 Visual Basic 프로그램에서 수행할 수 있습니다는 [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) 문.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
-   [사용 하 여 DLL에서 내보내기. DEF 파일](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec (dllexport)를 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C 언어 실행 파일에서 사용 하기 위해 c + + 함수 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [사용 하 여 사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)