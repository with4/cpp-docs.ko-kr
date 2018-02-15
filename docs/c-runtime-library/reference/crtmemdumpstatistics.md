---
title: "_CrtMemDumpStatistics | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtMemDumpStatistics
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
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 175497b0bd51a8c651af4662991f6b0b85c273f5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics
지정된 힙 상태에 대한 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `state`  
 덤프할 힙 상태에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `_CrtMemDumpStatistics` 함수는 지정된 힙 상태에 대한 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프합니다. 덤프 통계는 응용 프로그램에서 할당을 추적하고 메모리 문제를 감지하는 데 사용할 수 있습니다. 메모리 상태에는 특정 힙 상태나 두 상태 간의 차이가 포함될 수 있습니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtMemDumpStatistics` 호출이 제거됩니다.  
  
 `state` 매개 변수는 `_CrtMemDumpStatistics`가 호출되기 전에 [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md)에 의해 채워지거나 [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)에 의해 반환된 `_CrtMemState` 구조체에 대한 포인터여야 합니다. 검사점 생성 시 `state` 가 `NULL`인 경우 [Parameter Validation](../../c-runtime-library/parameter-validation.md)를 참조하세요. 계속해서 실행하도록 허용한 경우 `errno` 는 `EINVAL` 로 설정되고 아무 동작도 수행되지 않습니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 힙 상태 함수 및 `_CrtMemState` 구조에 대한 자세한 내용은 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|선택적 헤더|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
 **라이브러리:** 디버그 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)만 해당합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)