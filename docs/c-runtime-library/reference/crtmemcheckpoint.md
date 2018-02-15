---
title: "_CrtMemCheckpoint | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
dev_langs:
- C++
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37333b2b4621b9434a9fe1a924162957d5ea824f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint
디버그 힙의 현재 상태를 가져오고 응용 프로그램에서 제공한 `_CrtMemState` 구조에 저장합니다(디버그 버전만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void _CrtMemCheckpoint(  
   _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `state`  
 메모리 검사점으로 채울 `_CrtMemState` 구조에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `_CrtMemCheckpoint` 함수는 지정된 시점에 디버그 힙의 현재 상태에 대한 스냅숏을 만듭니다. 이 스냅숏은 메모리 누수를 비롯한 여러 문제를 손쉽게 감지하도록 [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) 같은 기타 힙 상태 함수에 사용할 수 있습니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtMemState` 호출이 제거됩니다.  
  
 응용 프로그램에서는 `_CrtMemState` 매개 변수의 Crtdbg.h에 정의된 대로 `state` 구조의 이전에 할당된 인스턴스에 포인터를 전달해야 합니다. 검사점 생성 시 `_CrtMemCheckpoint` 에서 오류가 발생하면 이 함수에서는 문제에 대해 설명하는 `_CRT_WARN` 디버그 보고서를 생성합니다.  
  
 힙 상태 함수 및 `_CrtMemState` 구조에 대한 자세한 내용은 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
 검사점 생성 시 `state` 가 `NULL`인 경우 [Parameter Validation](../../c-runtime-library/parameter-validation.md)를 참조하세요. 계속 실행하도록 허용된 경우 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)가 `EINVAL`로 설정되고 함수가 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h>, \<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
 **라이브러리:** 디버그 버전의 UCRT만 해당합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)