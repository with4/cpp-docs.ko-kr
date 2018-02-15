---
title: _set_abort_behavior | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d26f8339772854ab053c08deae3372ac567f9249
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="setabortbehavior"></a>_set_abort_behavior

프로그램이 비정상적으로 종료될 때 수행할 작업을 지정합니다.

> [!NOTE]
> 사용 하지 않는 `abort` 함수를 테스트 또는 디버깅 시나리오에서 Microsoft 스토어 앱의 경우를 제외 하 고 종료 합니다. 스토어 앱을 닫으려면 프로그래밍 또는 UI 방식으로에 따라 허용 되지 않습니다는 [Microsoft 스토어 정책](http://go.microsoft.com/fwlink/?LinkId=865936)합니다. 자세한 내용은 참조 [UWP 앱 수명 주기](http://go.microsoft.com/fwlink/p/?LinkId=865934)합니다.

## <a name="syntax"></a>구문

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>매개 변수

[in] _flags_  
`abort` 플래그의 새 값입니다.

[in] _mask_  
설정할 `abort` 플래그 비트의 마스크입니다.

## <a name="return-value"></a>반환 값

플래그의 이전 값입니다.

## <a name="remarks"></a>설명

`abort` 플래그에는 `_WRITE_ABORT_MSG` 및 `_CALL_REPORTFAULT`의 두 가지가 있습니다. `_WRITE_ABORT_MSG`는 프로그램이 비정상적으로 종료될 때 유용한 텍스트 메시지를 인쇄할지를 결정합니다. 이 메시지는 응용 프로그램이 `abort` 함수를 호출했음을 설명합니다. 기본 동작은 메시지를 인쇄하는 것입니다. `_CALL_REPORTFAULT`는 설정하는 경우 `abort` 호출 시 Watson 크래시 덤프가 생성되어 보고되도록 지정합니다. 기본적으로 DEBUG가 아닌 모드에서는 크래시 덤프 보고가 사용하도록 설정됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`_set_abort_behavior`|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예

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

## <a name="see-also"></a>참고 항목

[abort](../../c-runtime-library/reference/abort.md)  
