---
title: _CrtSetReportHook | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: faa7e5726555ef8000cd393f8f2f7061024095ed
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook

클라이언트 정의 보고 함수를 C 런타임 디버그 보고 프로세스에 연결함으로써 설치합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
_CRT_REPORT_HOOK _CrtSetReportHook(
   _CRT_REPORT_HOOK reportHook
);
```

### <a name="parameters"></a>매개 변수

*reportHook*<br/>
C 런타임 디버그 보고 프로세스에 연결할 새로운 클라이언트 정의 보고 함수입니다.

## <a name="return-value"></a>반환 값

이전 클라이언트 정의 보고 함수를 반환합니다.

## <a name="remarks"></a>설명

**_CrtSetReportHook** 보고 프로세스는 C 런타임 디버그 라이브러리에 자체 보고 함수를 사용 하도록 응용 프로그램을 허용 합니다. 결과적으로 [_CrtDbgReport](crtdbgreport-crtdbgreportw.md)가 호출되어 디버그 보고서를 생성할 때마다 응용 프로그램의 보고 함수가 먼저 호출됩니다. 이 기능을 사용 하면 특정 할당 형식에 맞게 또는 보고서를 사용 하 여 사용할 수 없는 대상으로 보낼 수 있도록 디버그 보고서를 필터링 같은 작업을 수행 하는 응용 프로그램 **_CrtDbgReport**합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtSetReportHook** 전처리 중 제거 됩니다.

보다 강력한 버전에 대 한 **_CrtSetReportHook**, 참조 [_CrtSetReportHook2](crtsetreporthook2-crtsetreporthookw2.md)합니다.

**_CrtSetReportHook** 함수 설치 클라이언트 정의 보고 함수에 지정 된 새 *reportHook* 이전 클라이언트 정의 후크를 반환 합니다. 다음 예제에서는 클라이언트 정의 보고서 후크가 어떻게 프로토타입화되어야 하는지를 보여 줍니다.

```C
int YourReportHook( int reportType, char *message, int *returnValue );
```

여기서 *reportType* 디버그 보고서 유형 (**_CRT_WARN**, **_CRT_ERROR**, 또는 **_CRT_ASSERT**), *메시지* , 보고서에 포함 된 완벽 하 게 어셈블된 디버그 사용자 메시지 및 **returnValue** 클라이언트에서 정의 된 지정 된 값으로 반환 되어야 하는 함수를 보고 **_ CrtDbgReport**합니다. 사용 가능한 보고서 형식에 대한 자세한 설명은 [_CrtSetReportMode](crtsetreportmode.md) 함수를 참조하세요.

클라이언트 정의 보고 함수는 완전히 필요한가 더 이상 보고 하지 않으려면 디버그 메시지를 처리, 함수 반환 해야 **TRUE**합니다. 함수가 반환 하는 경우 **FALSE**, **_CrtDbgReport** 보고서 유형, 모드 및 파일에 대 한 현재 설정을 사용 하 여 디버그 보고서를 생성 하기 위해 호출 됩니다. 또한를 지정 하 여는 **_CrtDbgReport** 반환 값에 **returnValue**, 응용 프로그램 디버그 중단 발생 하는지 여부를 제어할 수 있습니다. 디버그 보고서 구성 되 고 생성 되는 방법에 대 한 전체 설명은 참조 하세요. **_CrtSetReportMode**, [_CrtSetReportFile](crtsetreportfile.md), 및 **_CrtDbgReport**합니다.

다른 후크 가능 런타임 함수를 사용하고 고유한 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은 [디버그 후크 함수 작성](/visualstudio/debugger/debug-hook-function-writing)을 참조하세요.

> [!NOTE]
> 응용 프로그램은 컴파일된 경우 **/clr** 및 보고 함수를 호출 응용 프로그램이 종료 될 때 주, 보고 함수 모든 CRT 함수를 호출 하는 경우 CLR에서 예외가 throw 됩니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_CrtSetReportHook**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetReportHook](crtgetreporthook.md)<br/>
