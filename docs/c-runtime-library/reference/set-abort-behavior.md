---
title: "_set_abort_behavior | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_abort_behavior"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_abort_behavior"
  - "set_abort_behavior"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_abort_behavior 함수"
  - "프로그램 중단"
  - "set_abort_behavior 함수"
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _set_abort_behavior
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램이 비정상적으로 종료되었을 때 수행할 작업을 지정합니다.  
  
> [!NOTE]
>  테스트 또는 디버깅 시나리오를 제외하고는 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱을 종료하기 위해 `abort` 함수를 사용하지 마십시오.  프로그래밍 또는 UI 방식으로 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램을 닫는 것은 [Windows 8 응용 프로그램 인증 요구 사항](http://go.microsoft.com/fwlink/?LinkId=262889)에 따라 허용되지 않습니다.  자세한 내용은 [응용 프로그램 수명 주기\(Windows 스토어 응용 프로그램\)](http://go.microsoft.com/fwlink/?LinkId=262853)를 참조하십시오.  
  
## 구문  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### 매개 변수  
 \[in\] `flags`  
 `abort` 플래그의 새 값입니다.  
  
 \[in\] `mask`  
 설정할 `abort` 플래그 비트를 표시합니다.  
  
## 반환 값  
 플래그의 이전 값입니다.  
  
## 설명  
 `_WRITE_ABORT_MSG`와 `_CALL_REPORTFAULT`의 두 가지 `abort` 플래그가 있습니다.  `_WRITE_ABORT_MSG`는 프로그램이 비정상적으로 종료될 때 유용한 텍스트 메시지를 인쇄할지 여부를 결정합니다.  메시지는 응용 프로그램이 `abort` 함수를 호출했다고 합니다.  기본 동작은 메시지를 인쇄하는 것입니다.  `_CALL_REPORTFAULT`는 설정된 경우 `abort`을 호출할 때 Watson 크래시 덤프가 생성 및 보고되도록 지정합니다.  기본적으로 크래시 덤프 보고는 디버그가 아닌 빌드에 사용할 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_set_abort_behavior`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```c  
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
  
  **중단 메시지를 억제합니다.  성공하면 이 메시지만 출력됩니다.**    
## 참고 항목  
 [abort](../../c-runtime-library/reference/abort.md)