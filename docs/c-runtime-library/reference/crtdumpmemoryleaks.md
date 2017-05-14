---
title: "_CrtDumpMemoryLeaks | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDumpMemoryLeaks
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
dev_langs:
- C++
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6a4a5c78b4301158d1f0d23f588d6afe353104a0
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks
메모리 누수가 발생한 경우 디버그 힙의 모든 메모리 블록을 덤프합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## <a name="return-value"></a>반환 값  
 메모리 누수가 발견되면 `_CrtDumpMemoryLeaks`는 TRUE를 반환합니다. 그렇지 않은 경우 이 함수는 FALSE를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtDumpMemoryLeaks` 함수는 프로그램이 실행된 이후 메모리 누수가 발생했는지 확인합니다. 누수를 발견하면 힙에 있는 모든 개체에 대한 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프합니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtDumpMemoryLeaks` 호출이 제거됩니다.  
  
 응용 프로그램에서 할당한 메모리가 모두 해제되었는지 확인하기 위해 프로그램 실행의 끝에서 `_CrtDumpMemoryLeaks`가 자주 호출됩니다. [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 함수를 사용하여 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 `_CRTDBG_LEAK_CHECK_DF` 비트 필드를 켜면 프로그램 종료 시 함수가 자동으로 호출될 수 있습니다.  
  
 `_CrtDumpMemoryLeaks`는 [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md)를 호출하여 힙의 현재 상태를 가져온 후 해제되지 않은 블록에 대한 상태를 검사합니다. 해제되지 않은 블록이 발견되면 `_CrtDumpMemoryLeaks`는 [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md)를 호출하여 프로그램 실행 시작부터 힙에 할당된 모든 개체에 대한 정보를 덤프합니다.  
  
 기본적으로 내부 C 런타임 블록(`_CRT_BLOCK`)은 메모리 덤프 작업에 포함되지 않습니다. [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 함수는 `_CRTDBG_CHECK_CRT_DF` 비트의 `_crtDbgFlag`를 설정하여 이러한 블록을 누수 검색 프로세스에 포함하는 데 사용할 수 있습니다.  
  
 힙 상태 함수 및 `_CrtMemState` 구조체에 대한 자세한 내용은 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예제  
 `_CrtDumpMemoryLeaks`를 사용하는 방법에 대한 샘플은 [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)
