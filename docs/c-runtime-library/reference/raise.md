---
title: "raise | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "raise"
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
  - "Raise"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "프로그램[C++], 실행 중인 프로그램에 신호 보내기"
  - "raise 함수"
  - "신호"
  - "신호, 실행 중인 프로그램에 보내기"
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# raise
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

실행 중인 프로그램에 신호를 보냅니다.  
  
> [!NOTE]
>  테스트 또는 디버깅 시나리오에서를 제외하고는 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램을 종료하기 위해 이 메서드를 사용하지 마십시오.  프로그래밍 또는 UI 방식으로 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램을 닫는 것은 [Windows 8 응용 프로그램 인증 요구 사항](http://go.microsoft.com/fwlink/?LinkId=262889)의 섹션 3.6에 따라서 허용되지 않습니다.  자세한 내용은 [응용 프로그램 수명 주기\(Windows 스토어 응용 프로그램\)](http://go.microsoft.com/fwlink/?LinkId=262853)를 참조하십시오.  
  
## 구문  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### 매개 변수  
 *sig*  
 신호를 발생 합니다.  
  
## 반환 값  
 성공하면 **raise** 는 0을 반환합니다.  그렇지 않으면 0이 아닌 값을 반환 합니다.  
  
## 설명  
 이 **raise** 함수는 실행 중인 프로그램에게 *sig* 을 보냅니다.  이 **신호** 인 이전의 호출이 *sig* 를 위해 신호 처리를 설치했었던 경우, **발생** 는 함수를 실행합니다.  어떤 초리기 함수도 설치되지 않았으면, 신호 값 *sig* 와 관계되었던 기본 동작은 다음과 같이 취해집니다.  
  
|신호|의미|기본|  
|--------|--------|--------|  
|`SIGABRT`|Abnormal termination|종료 코드 3로 호출하는 프로그램을 종료합니다.|  
|`SIGFPE`|부동 소수점 오류|호출 프로그램을 종료합니다.|  
|`SIGILL`|잘못된 명령|호출 프로그램을 종료합니다.|  
|`SIGINT`|CTRL\+C 인터럽트|호출 프로그램을 종료합니다.|  
|`SIGSEGV`|잘못된 저장소 액세스|호출 프로그램을 종료합니다.|  
|`SIGTERM`|전송 프로그램 종료 요청|신호를 무시합니다.|  
  
 인수가 신호 위의 지정된 유효한 신호가 아닌 경우, 잘못된 매개변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)로 설명되어 호출됩니다.  처리되지 않는 경우, 함수는 0이 아닌 값을 반환하고 `EINVAL` 를 `errno` 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**raise**|\<signal.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [신호](../../c-runtime-library/reference/signal.md)