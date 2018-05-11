---
title: 지연 로드 도우미 함수의 Visual c + + 6.0 이후 DLL 변경 내용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3af68e5ba92a96502e295e75520cd182b4633dae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용
사용자 도우미 함수를 정의한 경우 있습니다 영향을 받을 수 또는 컴퓨터에 여러 버전의 Visual c + +를 있는 경우 변경 내용을 DLL 지연 로드 도우미 함수의 합니다. 예를 들어:  
  
-   **__delayLoadHelper** 이제 **__delayLoadHelper2**  
  
-   **__pfnDliNotifyHook** 이제 **__pfnDliNotifyHook2**  
  
-   **__pfnDliFailureHook** 이제 **__pfnDliFailureHook2**  
  
-   **__FUnloadDelayLoadedDLL** 이제 **__FUnloadDelayLoadedDLL2**  
  
> [!NOTE]
>  기본 도우미 함수를 사용 하는 경우 이러한 변경 하면 영향을 주지 않습니다. 링커를 호출 하는 방법에 대 한 변경 내용이 있습니다.  
  
## <a name="multiple-versions-of-visual-c"></a>여러 버전의 Visual c + +  
 여러 버전의 Visual c + + 사용자의 컴퓨터에 있으면 링커에서 delayimp.lib를 일치 하는지 확인 합니다. 링커 오류가 받아볼 수는 불일치가 있을 경우 `___delayLoadHelper2@8` 또는 `___delayLoadHelper@8` 으로 확인 되지 않은 외부 기호입니다. 전자는 이전 delayimp.lib 사용 하 여 새 링커가 의미 하 고 기능을 사용할 수는 이전 링커 새 때 delayimp.lib 사용 합니다.  
  
 확인 되지 않은 링커 오류가 발생 하는 경우 실행 [/linkermember dumpbin](../../build/reference/linkermember.md): delayimp.lib 도우미 함수는 도우미 함수는 대신 정의 참조를 포함 해야 하는 1입니다. 개체 파일;에 도우미 함수를 정의할 수도 수 있습니다. 실행 [dumpbin /symbols](../../build/reference/symbols.md) 를 찾아서 `delayLoadHelper(2)`합니다.  
  
 알고 있는 경우 Visual c + + 6.0 링커 다음 가지:  
  
-   정의 하는지 여부를 결정 하는 지연 로드 도우미.lib 또는.obj 파일에 대해 dumpbin 실행 **__delayLoadHelper2**합니다. 그렇지 않은 경우 링크 실패 합니다.  
  
-   정의 **__delayLoadHelper** 지연 될 수 있음을 도우미.lib 또는.obj 파일을 로드 합니다.  
  
## <a name="user-defined-helper-function"></a>사용자 지정 도우미 함수  
 사용자 도우미 함수를 정의 하 고 현재 버전의 Visual c + +를 사용 하는 경우 다음을 수행 합니다.  
  
-   도우미 함수의 이름 바꾸기 **__delayLoadHelper2**합니다.  
  
-   절대 주소 (VAs) Rva (상대 주소) 두 32 비트 및 64 비트 프로그램에서 예상 대로 작동 하도록 지연 설명자 (delayimp.h에 ImgDelayDescr)에서 포인터가 변경 된 포인터에 대 한이 다시 변환 해야 합니다. 새 함수 도입 되었습니다: delayhlp.cpp에서 찾을 PFromRva 합니다. 두 32 비트 또는 64 비트 포인터도 다시 변환 하기 위해 각각의 설명자에서 필드에이 함수를 사용할 수 있습니다. 기본 지연 로드 도우미 함수 여전히 좋은 예로 사용할 템플릿입니다.  
  
## <a name="load-all-imports-for-a-delay-loaded-dll"></a>지연 로드 된 DLL에 대 한 모든 가져오기 로드  
 링커 지연 로드 하도록 지정 하는 DLL에서 모든 가져오기를 로드할 수 있습니다. 참조 [지연 로드 된 DLL에 대 한 모든 가져오기 로드](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [도우미 함수 이해](understanding-the-helper-function.md)