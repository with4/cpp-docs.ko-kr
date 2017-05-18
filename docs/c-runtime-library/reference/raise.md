---
title: raise | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- raise
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
- Raise
dev_langs:
- C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 9cfcedc524b94d0aa6c381416c445cf62f9cf2fb
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="raise"></a>raise
실행 중인 프로그램에 신호를 보냅니다.  
  
> [!NOTE]
>  테스트 또는 디버깅 시나리오에서를 제외하고는 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램을 종료하기 위해 이 메서드를 사용하지 마십시오. 프로그래밍 또는 UI 방식으로 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱을 닫는 것은 [Windows 8 앱 인증 요구 사항](http://go.microsoft.com/fwlink/?LinkId=262889)의 섹션 3.6에 따라 허용되지 않습니다. 자세한 내용은 [응용 프로그램 수명 주기(Windows 스토어 앱)](http://go.microsoft.com/fwlink/?LinkId=262853)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *sig*  
 생성할 신호입니다.  
  
## <a name="return-value"></a>반환 값  
 **raise**는 정상적으로 실행되면 0을 반환합니다. 그렇지 않으면 0이 아닌 값을 반환합니다.  
  
## <a name="remarks"></a>설명  
 **raise** 함수는 *sig*를 실행 프로그램으로 보냅니다. 이전의 **signal** 호출에서 *sig*용 신호 처리 함수를 설치한 경우 **raise**는 해당 함수를 실행합니다. 처리기 함수가 설치되지 않은 경우에는 다음과 같이 신호 값 *sig*와 연결된 기본 작업이 수행됩니다.  
  
|신호|의미|Shared|  
|------------|-------------|-------------|  
|`SIGABRT`|비정상적인 종료|호출 프로그램을 종료하고 종료 코드 3을 생성합니다.|  
|`SIGFPE`|부동 소수점 오류|호출 프로그램을 종료합니다.|  
|`SIGILL`|잘못된 명령|호출 프로그램을 종료합니다.|  
|`SIGINT`|CTRL+C 인터럽트|호출 프로그램을 종료합니다.|  
|`SIGSEGV`|잘못된 저장소 액세스|호출 프로그램을 종료합니다.|  
|`SIGTERM`|프로그램에 종료 요청이 전송됨|신호를 무시합니다.|  
  
 인수가 위에 지정되어 있는 유효한 신호가 아니면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 신호가 처리되지 않은 경우 함수는 `errno`를 `EINVAL`로 설정하고 0이 아닌 값을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|**raise**|\<signal.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [signal](../../c-runtime-library/reference/signal.md)
