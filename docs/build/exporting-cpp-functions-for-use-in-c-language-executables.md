---
title: C 언어 실행 파일에서 사용 하기 위해 c + + 함수를 내보내는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf5f348675752ff9c0b548693c442812fa6be697
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367588"
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기  
  
C 언어 모듈에서 액세스 하려면, c + + 링크 하는 대신 C 링크가 있는 이러한 함수를 선언 해야 c + +로 작성 된 DLL에 함수를 포함 하는 경우. C + + 컴파일러 다르게 지정 되지 않은 경우 형식이 안전한 명명 규칙 (이름 데코레이션이 라고도 함)를 c + + 및 c + + 호출 규칙 3. 호출 하기 어려울 수 있는 사용  
  
C 링크를 지정 하려면 지정 `extern "C"` 함수 선언에 대 한 합니다. 예를 들어:  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [.Def 파일을 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec (dllexport)를 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS를 사용 하 여 가져오기 및 내보내기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 또는 c + + 언어 실행 파일에서 사용 하기 위해 내보내기 C 함수](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec (dllimport)을 사용 하 여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
-   [extern을 사용하여 링크 지정](../cpp/using-extern-to-specify-linkage.md)  
  
## <a name="see-also"></a>참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)