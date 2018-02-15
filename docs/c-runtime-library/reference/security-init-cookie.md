---
title: __security_init_cookie | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c51e02a36df9a54d2f301eafc24a0181e97153f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="securityinitcookie"></a>__security_init_cookie
전역 보안 쿠키를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __security_init_cookie(void);  
```  
  
## <a name="remarks"></a>설명  
 전역 보안 쿠키는 [/GS(버퍼 보안 검사)](../../build/reference/gs-buffer-security-check.md)를 사용하여 컴파일된 코드와 예외 처리를 사용하는 코드에서 버퍼 오버런을 방지하는 데 사용됩니다. 오버런 방지 함수로 진입 시 쿠키가 스택에 배치되며 해당 함수 종료 시 스택의 값을 전역 쿠키와 비교합니다. 쿠키의 값이 서로 다르면 버퍼 오버런이 발생한 것이며 프로그램이 즉시 종료됩니다.  
  
 일반적으로는 CRT가 초기화 시에 `__security_init_cookie`를 호출합니다. [/ENTRY](../../build/reference/entry-entry-point-symbol.md)를 사용하여 진입점을 지정하는 등의 방법으로 CRT 초기화를 바이패스하는 경우에는 `__security_init_cookie`를 직접 호출해야 합니다. `__security_init_cookie`를 호출하지 않으면 전역 보안 쿠키가 기본값으로 설정되며 버퍼 오버런 방지가 정상적으로 작동하지 않습니다. 공격자는 이 기본 쿠키 값을 악용하여 버퍼 오버런 검사를 통과할 수 있으므로 진입점을 직접 정의할 때는 항상 `__security_init_cookie`를 호출하는 것이 좋습니다.  
  
 `__security_init_cookie`는 오버런 방지 함수에 진입하기 전에 호출해야 합니다. 그렇지 않으면 가상 버퍼 오버런이 검색됩니다. 자세한 내용은 [C 런타임 오류 R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)를 참조하세요.  
  
## <a name="example"></a>예  
 [C 런타임 오류 R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)의 예제를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`__security_init_cookie`|\<process.h>|  
  
 `__security_init_cookie`는 표준 C 런타임 라이브러리에 대한 Microsoft 확장입니다. 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 보안 심층 검사](http://go.microsoft.com/fwlink/p/?linkid=7260)