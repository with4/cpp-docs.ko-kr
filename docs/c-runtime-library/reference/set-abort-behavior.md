---
title: _set_abort_behavior | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb308e527cc955d91af0b12547d52aa5e6316af5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407277"
---
# <a name="setabortbehavior"></a>_set_abort_behavior

프로그램이 비정상적으로 종료될 때 수행할 작업을 지정합니다.

> [!NOTE]
> 사용 하지 않는 [중단](abort.md) 함수를 테스트 또는 디버깅 시나리오에서 Microsoft 스토어 앱의 경우를 제외 하 고 종료 합니다. 스토어 앱을 닫으려면 프로그래밍 또는 UI 방식으로에 따라 허용 되지 않습니다는 [Microsoft 스토어 정책](http://go.microsoft.com/fwlink/?LinkId=865936)합니다. 자세한 내용은 참조 [UWP 앱 수명 주기](http://go.microsoft.com/fwlink/p/?LinkId=865934)합니다.

## <a name="syntax"></a>구문

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>매개 변수

*flags*<br/>
새 값은 [중단](abort.md) 플래그입니다.

*마스크*<br/>
에 대 한 마스크는 [중단](abort.md) 설정 하는 비트 플래그를 지정 합니다.

## <a name="return-value"></a>반환 값

플래그의 이전 값입니다.

## <a name="remarks"></a>설명

두 개의 [중단](abort.md) 플래그: **_WRITE_ABORT_MSG** 및 **_CALL_REPORTFAULT**합니다. **_WRITE_ABORT_MSG** 유용한 텍스트 메시지 인쇄 프로그램이 비정상적으로 종료 될 때 결정 합니다. 응용 프로그램이 호출에 메시지에 상태가 [중단](abort.md) 함수입니다. 기본 동작은 메시지를 인쇄하는 것입니다. **_CALL_REPORTFAULT**경우 설정 Watson 크래시 덤프 생성 되 고 보고 하는 시기를 지정 하 고, [중단](abort.md) 호출 됩니다. 기본적으로 DEBUG가 아닌 모드에서는 크래시 덤프 보고가 사용하도록 설정됩니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>참고자료

[abort](abort.md)<br/>
