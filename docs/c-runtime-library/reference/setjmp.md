---
title: setjmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- setjmp
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
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc4673485577f5a12024d31e94063c82a8c7b8c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407254"
---
# <a name="setjmp"></a>setjmp

프로그램의 현재 상태를 저장합니다.

## <a name="syntax"></a>구문

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>매개 변수

*env*<br/>
환경이 저장되는 변수입니다.

## <a name="return-value"></a>반환 값

스택 환경에 저장한 후 0을 반환합니다. 경우 **setjmp** 의 결과로 반환는 **longjmp** 호출 반환 된 **값** 의 인수 **longjmp**, 또는 경우에는 **값**  의 인수 **longjmp** 은 0으로, **setjmp** 1을 반환 합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

**setjmp** 함수 저장 이후에 복원 하려면 사용 하는 스택 환경 **longjmp**합니다. 함께 사용 하면 **setjmp** 및 **longjmp** 로컬이 아닌를 실행 하는 방법을 제공 **goto**합니다. setjmp와 longjmp는 일반 호출이나 반환 규칙을 사용하지 않고 전에 호출된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달하는 데 주로 사용됩니다.

에 대 한 호출 **setjmp** 에서 현재 스택 환경을 저장 *env*합니다. 후속 호출에 **longjmp** 바로 뒤의 해당 지점에 제어를 반환 하 고 저장된 된 환경을 복원 **setjmp** 호출 합니다. 될 때가지고 있던 값을 포함 하는 모든 변수 (제외 레지스터 변수에) 컨트롤을 받는 루틴에 액세스할 수 있는 **longjmp** 호출 되었습니다.

사용할 수 없으면 **setjmp** 관리 코드와 네이티브 코드에서 이동할 수 있습니다.

**참고** **setjmp** 및 **longjmp** c + + 개체 의미 체계를 지원 하지 않습니다. C++ 프로그램에서는 C++ 예외 처리 메커니즘을 사용해야 합니다.

자세한 내용은 [setjmp 및 longjmp 사용](../../cpp/using-setjmp-longjmp.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**setjmp**|\<setjmp.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_fpreset](fpreset.md)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)<br/>
[_setjmp3](../../c-runtime-library/setjmp3.md)<br/>
