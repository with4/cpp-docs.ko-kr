---
title: __security_init_cookie | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
dev_langs:
- C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c905004702fe7a767ea7d91285a66d6b91465fd7
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="securityinitcookie"></a>__security_init_cookie

전역 보안 쿠키를 초기화합니다.

## <a name="syntax"></a>구문

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>설명

전역 보안 쿠키는 [/GS(버퍼 보안 검사)](../../build/reference/gs-buffer-security-check.md)를 사용하여 컴파일된 코드와 예외 처리를 사용하는 코드에서 버퍼 오버런을 방지하는 데 사용됩니다. 오버런 방지 함수로 진입 시 쿠키가 스택에 배치되며 해당 함수 종료 시 스택의 값을 전역 쿠키와 비교합니다. 쿠키의 값이 서로 다르면 버퍼 오버런이 발생한 것이며 프로그램이 즉시 종료됩니다.

일반적으로 **__security_init_cookie** 초기화 될 때 CRT에 의해 호출 됩니다. CRT 초기화를 바이패스 하는 경우-예를 들어, 사용 하는 경우 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 대 한 진입점을 지정 하려면-호출 해야 합니다 **__security_init_cookie** 직접 합니다. 경우 **__security_init_cookie** 를 호출 하지 않으면 전역 보안 쿠키가 기본값으로 설정 되 고 버퍼 오버런 방지 손상 됩니다. 공격자가이 기본 쿠키 값을 버퍼 오버런 검사 무력화 악용할 수 있습니다, 때문에 항상 호출 하는 것이 좋습니다 **__security_init_cookie** 직접 진입점을 정의 하는 경우.

에 대 한 호출 **__security_init_cookie** 오버런 방지 전에 만들어야 함수를 입력, 그렇지 않으면 가상 버퍼 오버런이 검색 됩니다. 자세한 내용은 [C 런타임 오류 R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)를 참조하세요.

## <a name="example"></a>예제

[C 런타임 오류 R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)의 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**__security_init_cookie**|\<process.h>|

**__security_init_cookie** 표준 C 런타임 라이브러리에는 Microsoft 확장입니다. 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[컴파일러 보안 심층 검사](http://go.microsoft.com/fwlink/p/?linkid=7260)<br/>
