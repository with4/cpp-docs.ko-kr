---
title: "_CrtCheckMemory | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
dev_langs: C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60909079a4d7c30b3a3e6c00257d882d76467585
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory
디버그 힙에서 할당된 메모리 블록의 무결성을 확인합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
  
int _CrtCheckMemory( void );  
```  
  
## <a name="return-value"></a>반환 값  
 성공하면 `_CrtCheckMemory`에서 TRUE를 반환합니다. 실패하면 함수에서 FALSE를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtCheckMemory` 함수는 기초적인 기본 힙을 확인하고 모든 메모리 블록을 검사하여 디버그 힙 관리자가 할당한 메모리의 유효성을 검사합니다. 기초적인 기본 힙, 디버그 헤더 정보 또는 덮어쓰기 버퍼에서 오류 또는 메모리 불일치가 발견되면 `_CrtCheckMemory` 함수는 오류 조건을 설명하는 정보가 포함된 디버그 보고서를 생성합니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtCheckMemory` 호출이 제거됩니다.  
  
 `_CrtCheckMemory`의 동작은 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 함수를 사용하여 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 비트 필드를 설정함으로써 제어할 수 있습니다. **_CRTDBG_CHECK_ALWAYS_DF** 비트 필드를 켜면 메모리 할당 작업이 요청될 때마다 `_CrtCheckMemory`가 호출됩니다. 이 메서드는 실행 속도를 늦추지만, 오류를 신속하게 catch하는 데 유용합니다. **_CRTDBG_ALLOC_MEM_DF** 비트 필드를 끄면 `_CrtCheckMemory`가 힙을 확인하지 않고 **TRUE**를 즉시 반환합니다.  
  
 이 함수는 **TRUE** 또는 **FALSE**를 반환하므로 이를 [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로 중 하나로 전달하여 간단한 디버깅 오류 처리 메커니즘을 만들 수 있습니다. 다음 예제에서는 힙에서 손상이 검색된 경우 어설션 실패가 발생합니다.  
  
```  
_ASSERTE( _CrtCheckMemory( ) );  
```  
  
 `_CrtCheckMemory`를 다른 디버그 함수와 함께 사용할 수 있는 방법에 대한 자세한 내용은 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 메모리 관리 및 디버그 힙의 개요는 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_CrtCheckMemory`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예  
 `_CrtCheckMemory`를 사용하는 방법에 대한 샘플은 [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)