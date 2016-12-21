---
title: "_free_locale | Microsoft Docs"
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
  - "_free_locale"
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
  - "__free_locale"
  - "free_locale"
  - "_free_locale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__free_locale 함수"
  - "_free_locale 함수"
  - "free_locale 함수"
  - "로캘, 해제"
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _free_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로캘 개체를 해제합니다.  
  
## 구문  
  
```  
void _free_locale(  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `locale`  
 해제할 로캘 개체입니다.  
  
## 설명  
 `_free_locale` 함수는 `_get_current_locale` 또는 `_create_locale` 에 대한 호출에서 얻어지는 로캘 개체를 해제하기 위해 사용 됩니다.  
  
 이 함수의 이전 이름인 `__free_locale` \(두 개의 선행 밑줄\)은 사용 되지 않습니다.  
  
## 요구 사항  
  
|`Routine`|필수 헤더|  
|---------------|-----------|  
|`_free_locale`|\<locale.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항이 없습니다.  
  
## 참고 항목  
 [\_get\_current\_locale](../../c-runtime-library/reference/get-current-locale.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)