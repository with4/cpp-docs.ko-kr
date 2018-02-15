---
title: "_CrtSetReportHook | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8c7b3a8954c39e8157834297ab5ac3a747420af8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook
클라이언트 정의 보고 함수를 C 런타임 디버그 보고 프로세스에 연결함으로써 설치합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `reportHook`  
 C 런타임 디버그 보고 프로세스에 연결할 새로운 클라이언트 정의 보고 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 이전 클라이언트 정의 보고 함수를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtSetReportHook`를 사용하면 응용 프로그램이 C 런타임 디버그 라이브러리 보고 프로세스에 고유한 보고 함수를 사용할 수 있습니다. 결과적으로 [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)가 호출되어 디버그 보고서를 생성할 때마다 응용 프로그램의 보고 함수가 먼저 호출됩니다. 이 기능을 통해 응용 프로그램이 디버그 보고서 필터링과 같은 작업을 수행할 수 있어 특정 할당 형식에 집중하거나 `_CrtDbgReport`의 사용을 통해 이용할 수 없는 대상에 보고서를 보낼 수 있습니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtSetReportHook` 호출이 제거됩니다.  
  
 더욱 강력한 버전의 `_CrtSetReportHook`에 대해서는 [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)를 참조하세요.  
  
 `_CrtSetReportHook` 함수는 `reportHook`에 지정된 새로운 클라이언트 정의 보고 함수를 설치하고 이전의 클라이언트 정의 후크를 반환합니다. 다음 예제에서는 클라이언트 정의 보고서 후크가 어떻게 프로토타입화되어야 하는지를 보여 줍니다.  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 여기서 `reportType`은 디버그 보고서 형식(`_CRT_WARN`, `_CRT_ERROR` 또는 `_CRT_ASSERT`)이며, `message`는 보고서에 포함할 완전히 어셈블된 디버그 사용자 메시지이고, `returnValue`는 `_CrtDbgReport`에 의해 반환되어야 하는 클라이언트 정의 보고 함수에서 지정한 값입니다. 사용 가능한 보고서 형식에 대한 자세한 설명은 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 함수를 참조하세요.  
  
 클라이언트 정의 보고 함수에서 추가 보고가 필요하지 않도록 디버그 메시지를 완벽하게 처리하면 함수가 `TRUE`를 반환합니다. 함수가 `FALSE`를 반환하는 경우 `_CrtDbgReport`가 호출되어 보고서 형식, 모드 및 파일에 대한 현재 설정을 사용하여 디버그 보고서를 생성합니다. 또한 `returnValue`에 `_CrtDbgReport` 반환 값을 지정하여 응용 프로그램이 디버그 중단 발생 여부도 제어할 수 있습니다. 디버그 보고서를 구성하고 생성하는 방법에 대한 자세한 설명은 `_CrtSetReportMode`, [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) 및 `_CrtDbgReport`를 참조하세요.  
  
 다른 후크 가능 런타임 함수를 사용하고 고유한 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은 [디버그 후크 함수 작성](/visualstudio/debugger/debug-hook-function-writing)을 참조하세요.  
  
> [!NOTE]
>  `/clr`을 사용하여 응용 프로그램을 컴파일했는데 응용 프로그램이 main 함수를 종료한 후 보고 함수가 호출되는 경우 보고 함수에서 CRT 함수를 호출하면 CLR에서 예외를 throw합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_CrtSetReportHook`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)