---
title: C 런타임 오류 R6035 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6035
dev_langs:
- C++
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecadf1793475e1cf5f354796c71a1894884e24e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="c-runtime-error-r6035"></a>C 런타임 오류 R6035
Microsoft Visual c + + 런타임 라이브러리, 오류 R6035-이 응용 프로그램의 모듈을 초기화 하 고 모듈의 전역 보안 쿠키 보안 쿠키에 의존 하는 함수를 활성화 합니다.  이전 __security_init_cookie를 호출 합니다.  
  
 [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) 전역 보안 쿠키를 처음 사용 하기 전에 호출 해야 합니다.  
  
 로 컴파일된 코드에서 버퍼 오버런 방지에 대 한 전역 보안 쿠키를 사용 하는 [/GS (버퍼 보안 검사)](../../build/reference/gs-buffer-security-check.md) 코드에서 구조적된 예외 처리를 사용 하 고 있습니다. 기본적으로, 오버런 방지 함수에 입력 시 쿠키가 스택에 배치 되 고 종료 스택에 값 전역 쿠키에 대해 비교 됩니다. 값이 서로 다르면 버퍼 오버런이 발생 하는 프로그램의 즉시 종료를 나타냅니다.  
  
 오류 R6035 나타냅니다에 대 한 호출 `__security_init_cookie` 이후 보호 된 함수를 입력 했습니다. 계속 하려면 실행 되었으면 가상 버퍼 오버런이 스택에 쿠키 전역 쿠키 더 이상 일치 하기 때문에 감지 됩니다.  
  
 예를 들어 다음 DLL입니다. DLL 진입점 링커를 통해 즉 DllEntryPoint로 설정 되어 [/ENTRY (진입점 기호)](../../build/reference/entry-entry-point-symbol.md) 옵션입니다. 이 메서드는 전역 보안 쿠키 초기화 일반적으로 DLL 자체를 호출 해야 하므로 하는 CRT 초기화 `__security_init_cookie`합니다.  
  
```  
// Wrong way to call __security_init_cookie  
DllEntryPoint(...) {  
   DllInitialize();  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
  
void DllInitialize() {  
   __security_init_cookie();  
}  
```  
  
 이 예제에서는 즉 DllEntryPoint 구조적된 예외 처리를 사용 하 고 따라서 보안 쿠키를 사용 하 여 버퍼 오버런을 검색할 수 있으므로 오류 R6035 생성 됩니다. DllInitialize 라고 시점에서는 전역 보안 쿠키 이미 놓여진 스택에 있습니다.  
  
 이 예에서 올바른 방법은 보여 줍니다.  
  
```  
// Correct way to call __security_init_cookie  
DllEntryPoint(...) {  
   __security_init_cookie();  
   DllEntryHelper();  
}  
  
void DllEntryHelper() {  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
```  
  
 이 경우 즉 DllEntryPoint 버퍼 오버런 으로부터 보호 되지 않는 경우 (로컬 문자열 버퍼가 있으며 구조적된 예외 처리를 사용 하지 않는); 안전 하 게 호출할 수는 따라서 `__security_init_cookie`합니다. 다음 보호 되는 도우미 함수를 호출 합니다.  
  
> [!NOTE]
>  R6035는 오류 메시지만 x86에 의해 생성 된 디버그 CRT를 하 고 구조적된 예외 처리 하지만 조건에 대해서만 하 고 모든 형태의 예외에 대 한 모든 플랫폼에서 오류 처리 하는, c + + EH 같은 키를 누릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 보안 심층 검사](http://go.microsoft.com/fwlink/p/?linkid=7260)