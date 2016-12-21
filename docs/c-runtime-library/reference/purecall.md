---
title: "_purecall | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_purecall"
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
apitype: "DLLExport"
f1_keywords: 
  - "purecall"
  - "_purecall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_purecall 함수"
  - "purecall 함수"
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _purecall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 순수 가상 함수 호출 오류 처리기입니다. 컴파일러는 순수 가상 멤버 함수를 호출 하는 경우이 함수를 호출 하는 코드를 생성 합니다.  
  
## 구문  
  
```  
extern "C" int __cdecl _purecall();  
```  
  
## 설명  
 `_purecall` 함수는 Microsoft Visual c \+ \+ 컴파일러의 Microsoft 관련 구현 세부 정보입니다. 이 함수는 프로그램 코드에서 직접 호출할 수 없습니다 되었으며 없는 공용 헤더 선언 해야 합니다. C 런타임 라이브러리의 공용 내보내기는 이기 때문에 여기 설명 되어 있습니다.  
  
 순수 가상 함수에 대 한 호출 구현이 없는 되었기 때문에 오류입니다. 컴파일러를 호출 하는 코드를 생성 된 `_purecall` 순수 가상 함수를 호출 하는 경우 오류 처리기 함수입니다. 기본적으로 `_purecall` 프로그램을 종료 합니다. 종료 하기 전에 `_purecall` 함수가 호출 하는 `_purecall_handler` 프로세스에 대해 설정 된 경우 작동 합니다. 사용자 고유의 오류 처리기 함수에 대 한 순수 가상 함수 호출, 디버깅 또는 보고를 목적으로 catch를 설치할 수 있습니다. 고유한 오류 처리기를 사용 하려면이 있는 함수를 만듭니다는 `_purecall_handler` 서명을 사용 하 여 [\_set\_purecall\_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md) 현재 처리기 되도록 합니다.  
  
## 요구 사항  
 `_purecall` 함수 헤더 선언은 없습니다.`_purecall_handler` typedef \< stdlib.h \>에 정의 됩니다.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_set\_purecall\_handler, \_get\_purecall\_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)