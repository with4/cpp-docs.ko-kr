---
title: 가져오기 및 내보내기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ee3ffe33dbb99f1f9b4124e2695d2e56dbe5544
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="importing-and-exporting"></a>가져오기 및 내보내기
응용 프로그램으로 공용 기호를 가져올 하거나 두 개의 메서드를 사용 하 여 DLL에서 함수를 내보낼 수 있습니다.  
  
-   DLL을 빌드할 때 모듈 정의 (.def) 파일을 사용 하 여  
  
-   키워드를 사용 하 여 **__declspec (dllimport)** 또는 **__declspec (dllexport)** 주 응용 프로그램의 함수 정의  
  
## <a name="using-a-def-file"></a>.Def 파일  
 모듈 정의 (.def) 파일은 DLL의 다양 한 특성을 설명 하는 하나 이상의 모듈 문을 포함 하는 텍스트 파일. 사용 하지 않는 경우 **__declspec (dllimport)** 또는 **__declspec (dllexport)** DLL DLL의 함수를 내보내려면.def 파일을 필요 합니다.  
  
 .Def 파일을 사용할 수 있습니다 [응용 프로그램으로 가져올](../build/importing-using-def-files.md) 또는 [DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)합니다.  
  
## <a name="using-declspec"></a>__Declspec를 사용 하 여  
 Visual c + + 사용 하 여 **__declspec (dllimport)** 및 **__declspec (dllexport)** 바꾸려면는 **__export** 16 비트 버전의 Visual c + +에서 이전에 사용 된 키워드입니다.  
  
 사용할 필요가 없습니다 **__declspec (dllimport)** 있으며 올바르게 컴파일되도록 하는 코드에 대 한 컴파일러가를 보다 효율적인 코드를 생성 합니다. 컴파일러는 함수에에서 있는지 여부를 DLL, 일반적으로 DLL 경계를 교차 하는 함수 호출에 수 간접 참조 수준을 컴파일러가 결정할 수 없기 때문에 보다 효율적인 코드를 생성할 수 있습니다. 하지만 사용 해야 **__declspec (dllimport)** DLL에서 사용 되는 변수를 가져오려는 합니다.  
  
 적절 한.def 파일의 EXPORTS 섹션으로 **__declspec (dllexport)** 필요 하지 않습니다. **__declspec (dllexport)** 쉽게.def 파일을 사용 하지 않고.exe 또는.dll 파일에서 함수를 내보낼 수 있는 방법을 제공 하기 위해 추가 되었습니다.  
  
 Win32 이식 가능한 실행 파일 형식이 가져오기를 수정 하기 위한 페이지 수를 최소화 하도록 설계 되었습니다. 이렇게 하려면 가져오기 주소 테이블 이라는 한 곳에서 모든 프로그램에 대 한 모든 가져오기 주소를 파악할 수 있습니다. 이렇게 하면 로더를이 가져오기에 액세스할 때만 하나 또는 두 개의 페이지를 수정할 수 있습니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)