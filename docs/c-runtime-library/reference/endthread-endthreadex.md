---
title: _endthread, _endthreadex | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4588829b3ec1d348405be925a75c493f4e8594b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397755"
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex

스레드를 종료 **_endthread** 에 의해 만들어진 스레드 종료 **_beginthread** 및 **_endthreadex** 에 의해 만들어진 스레드 종료 **_beginthreadex**.

## <a name="syntax"></a>구문

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>매개 변수

*retval* 스레드 종료 코드입니다.

## <a name="remarks"></a>설명

그러나 호출할 수 있습니다 **_endthread** 또는 **_endthreadex** 명시적으로 스레드를 종료할 **_endthread** 또는 **_endthreadex** 라고 자동으로에 대 한 매개 변수로 전달 된 스레드가 루틴에서 반환 하는 경우 **_beginthread** 또는 **_beginthreadex**합니다. 에 대 한 호출으로 스레드를 종료 **endthread** 또는 **_endthreadex** 스레드에 대 한 할당 된 리소스의 적절 한 복구 보장 합니다.

> [!NOTE]
> Libcmt.lib로 연결된 실행 파일의 경우 런타임 시스템이 할당된 리소스를 회수하지 않도록 Win32 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API를 호출하지 마세요. **_endthread** 및 **_endthreadex** 할당 된 스레드 리소스를 회수 한 다음 호출 **ExitThread**합니다.

**_endthread** 스레드 핸들을 자동으로 닫습니다. (이 동작은 Win32에서 **ExitThread** API입니다.) 따라서 사용 하는 경우 **_beginthread** 및 **_endthread**를 명시적으로 닫지 마세요 스레드 핸들 Win32를 호출 하 여 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API입니다.

같은 Win32 **ExitThread** API **_endthreadex** 스레드 핸들을 닫지 않습니다. 따라서 사용 하는 경우 **_beginthreadex** 및 **_endthreadex**, Win32를 호출 하 여 스레드 핸들을 닫아야 **CloseHandle** API입니다.

> [!NOTE]
> **_endthread** 및 **_endthreadex** c + + 소멸자 보류 중인 스레드를 호출할 수 있습니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

다중 스레드 버전의 유일한 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 입니다.

## <a name="example"></a>예제

[_beginthread](beginthread-beginthreadex.md)에 대한 예를 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
