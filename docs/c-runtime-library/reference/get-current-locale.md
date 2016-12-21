---
title: "_get_current_locale | Microsoft Docs"
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
  - "_get_current_locale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_current_locale"
  - "__get_current_locale"
  - "_get_current_locale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__get_current_locale 함수"
  - "_get_current_locale 함수"
  - "get_current_locale 함수"
  - "로캘, 정보 가져오기"
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_current_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 로캘을 나타내는 locale 개체를 가져옵니다.  
  
## 구문  
  
```  
_locale_t _get_current_locale(void);  
```  
  
## 반환 값  
 현재 로캘을 나타내는 locale 개체입니다.  
  
## 설명  
 `_get_current_locale`  함수는 현재 스레드에 설정된 로캘을 가져오고 해당 로캘을 나타내는 locale 개체를 반환합니다.  
  
 이 함수의 이전 이름인 `__get_current_locale` \(두 개의 선행 밑줄\)은 사용 되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_current_locale`|\<locale.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항이 없습니다.  
  
## 참고 항목  
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)