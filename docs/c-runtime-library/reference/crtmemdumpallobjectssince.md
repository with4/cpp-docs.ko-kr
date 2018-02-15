---
title: "_CrtMemDumpAllObjectsSince | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17a8f1cd518c0864006d836f551d99554d3cdf24
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince
프로그램 실행의 시작부터 또는 지정된 힙 상태에서 힙에 있는 개체에 대한 정보를 덤프합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
  
      void _CrtMemDumpAllObjectsSince(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `state`  
 덤프를 시작할 힙 상태 또는 **NULL**에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `_CrtMemDumpAllObjectsSince` 함수는 힙에 할당된 개체의 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프합니다. 덤프 정보는 응용 프로그램에서 할당을 추적하고 메모리 문제를 검색하는 데 사용할 수 있습니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtMemDumpAllObjectsSince` 호출이 제거됩니다.  
  
 `_CrtMemDumpAllObjectsSince`는 `state` 매개 변수의 값을 사용하여 덤프 작업을 시작할 위치를 결정합니다. 지정된 힙 상태에서 덤프를 시작하려면 `state` 매개 변수는 `_CrtMemDumpAllObjectsSince`가 호출되기 전에 [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md)에 의해 채워진 **_CrtMemState** 구조체에 대한 포인터여야 합니다. `state`가 **NULL**인 경우 함수는 프로그램 실행의 시작부터 덤프를 시작합니다.  
  
 응용 프로그램이 [_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md)를 호출하여 덤프 후크 함수를 설치한 경우 `_CrtMemDumpAllObjectsSince`는 `_CLIENT_BLOCK` 형식의 블록에 대한 정보를 덤프할 때마다 응용 프로그램에서 제공하는 덤프 함수도 호출합니다. 기본적으로 내부 C 런타임 블록(`_CRT_BLOCK`)은 메모리 덤프 작업에 포함되지 않습니다. [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 함수는 `_CRTDBG_CHECK_CRT_DF` 비트의 **_crtDbgFlag**를 설정하여 이러한 블록을 포함하는 데 사용할 수 있습니다. 또한 해제되거나 무시된 것으로 표시된 블록(**_FREE_BLOCK**, **_IGNORE_BLOCK**)은 메모리 덤프에 포함되지 않습니다.  
  
 힙 상태 함수 및 `_CrtMemState` 구조체에 대한 자세한 내용은 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예  
 `_CrtMemDumpAllObjectsSince`를 사용하는 방법에 대한 샘플은 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)