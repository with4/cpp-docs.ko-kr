---
title: "_CrtSetDumpClient | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb8a62dc903b7bb0684d3fffcde8a677200d665d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient
`_CLIENT_BLOCK` 형식 메모리 블록을 덤프하는 응용 프로그램 정의 함수를 설치합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dumpClient`  
 C 런타임 디버그 메모리 덤프 프로세스에 연결할 새로운 클라이언트 정의 메모리 덤프 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 이전에 정의된 클라이언트 블록 덤프 함수를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtSetDumpClient` 함수를 사용하면 응용 프로그램이 `_CLIENT_BLOCK` 메모리 블록에 저장된 개체를 덤프할 고유한 함수를 C 런타임 디버그 메모리 덤프 프로세스에 연결할 수 있습니다. 결과적으로 [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) 또는 [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md)와 같은 디버그 덤프 함수가 `_CLIENT_BLOCK` 메모리 블록을 덤프할 때마다 응용 프로그램의 덤프 함수도 호출됩니다. `_CrtSetDumpClient`는 메모리 누수를 감지하고 `_CLIENT_BLOCK` 블록에 저장된 데이터의 내용을 유효성 검사하거나 보고하기 위한 쉬운 방법을 응용 프로그램에 제공합니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtSetDumpClient` 호출이 제거됩니다.  
  
 `_CrtSetDumpClient` 함수는 `dumpClient`에 지정된 새로운 응용 프로그램 정의 덤프 함수를 설치하고 이전에 정의된 덤프 함수를 반환합니다. 클라이언트 블록 덤프 함수의 예제는 다음과 같습니다.  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 `userPortion` 인수는 메모리 블록에 있는 사용자 데이터 부분의 시작에 대한 포인터이며 `blockSize`는 할당된 메모리 블록의 크기를 바이트 단위로 지정합니다. 클라이언트 블록 덤프 함수는 `void`를 반환해야 합니다. `_CrtSetDumpClient`에 전달되는 클라이언트 덤프 함수에 대한 포인터는 Crtdbg.h에 정의된 대로 `_CRT_DUMP_CLIENT` 형식입니다.  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 `_CLIENT_BLOCK` 형식 메모리 블록에서 작동하는 함수에 대한 자세한 내용은 [클라이언트 블록 후크 함수](/visualstudio/debugger/client-block-hook-functions)를 참조하세요. [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md) 함수는 블록 형식과 하위 형식에 대한 정보를 반환하는 데 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)