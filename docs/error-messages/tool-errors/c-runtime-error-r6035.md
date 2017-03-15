---
title: "C 런타임 오류 R6035 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6035"
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# C 런타임 오류 R6035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+ 런타임 라이브러리 오류 R6035 \- 이 응용 프로그램의 모듈이 모듈의 전역 보안 쿠키를 초기화하고 있는데 해당 보안 쿠키를 사용하는 함수가 활성화되어 있습니다.  먼저 \_\_security\_init\_cookie를 호출하십시오.  
  
 전역 보안 쿠키를 처음 사용하기 전에 [\_\_security\_init\_cookie](../../c-runtime-library/reference/security-init-cookie.md)를 호출해야 합니다.  
  
 전역 보안 쿠키는 [\/GS\(버퍼 보안 검사\)](../../build/reference/gs-buffer-security-check.md)로 컴파일된 코드 및 구조적 예외 처리를 사용하는 코드에서 버퍼 오버런 보호에 사용됩니다.  기본적으로 오버런이 보호된 함수에 진입하면 스택에 쿠키가 배치되고 이 함수가 종료되면 스택에 있는 값이 전역 쿠키와 비교됩니다.  두 값이 서로 다르면 버퍼 오버런이 발생한 것이므로 프로그램이 즉시 종료됩니다.  
  
 R6035 오류는 보호된 함수에 진입한 이후 `__security_init_cookie`를 호출했음을 나타냅니다.  스택의 쿠키와 전역 쿠키가 더 이상 일치하지 않으므로 실행을 계속하면 의사 버퍼 오버런이 감지됩니다.  
  
 다음 DLL 예제를 살펴보십시오.  DLL 진입점이 [\/ENTRY\(진입점 기호\)](../../build/reference/entry-entry-point-symbol.md) 링커 옵션을 통해 DllEntryPoint로 설정됩니다.  이렇게 하면 전역 보안 쿠키를 정상적으로 초기화하는 CRT의 초기화를 건너뛰게 되므로 DLL 자체에서 `__security_init_cookie`를 호출해야 합니다.  
  
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
  
 이 예제에서는 DllEntryPoint에서 구조적 예외 처리를 사용하고 따라서 보안 쿠키를 사용하여 버퍼 오버런을 감지하므로 R6035 오류가 발생합니다.  DllInitialize가 호출되는 시점에서 전역 보안 쿠키는 이미 스택에 배치된 상태입니다.  
  
 다음 예제에서는 올바른 방법을 보여 줍니다.  
  
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
  
 이 경우 DllEntryPoint는 로컬 문자열 버퍼가 없고 구조적 예외 처리를 사용하지 않으므로 버퍼 오버런 보호를 받지 않습니다. 따라서 `__security_init_cookie`를 안전하게 호출할 수 있습니다.  그런 다음 보호되는 도우미 함수를 호출합니다.  
  
> [!NOTE]
>  R6035 오류 메시지는 x86 디버그 CRT에서만, 그리고 구조적 예외 처리에 대해서만 발생하지만 이 조건은 모든 플랫폼 및 모든 예외 처리 형태\(C\+\+ EH 등\)에서 오류입니다.  
  
## 참고 항목  
 [컴파일러 보안 상세 점검](http://go.microsoft.com/fwlink/?linkid=7260)