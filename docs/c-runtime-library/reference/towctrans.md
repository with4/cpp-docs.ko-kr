---
title: "towctrans | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "towctrans"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "towctrans"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "towctrans 함수"
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# towctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자를 변환합니다.  
  
## 구문  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### 매개 변수  
 `c`  
 변환할 문자입니다.  
  
 `category`  
 [wctrans](../../c-runtime-library/reference/wctrans.md). 의 반환값을 포함하는 식별자 입니다.  
  
## 반환 값  
 `towctrans` 다음의 문자 `c` 는 `category` 에서 변환에 사용 됩니다.  
  
## 설명  
 `category` 의 값은 반드시 [wctrans](../../c-runtime-library/reference/wctrans.md) 에 대한 이전 성공에 의해 반환되어야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`towctrans`|\<wctype.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 `towctrans` 사용에 대한 샘플은 `wctrans` 를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)