---
title: "_ismbbkana, _ismbbkana_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbkana_l"
  - "_ismbbkana"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbbkana_l"
  - "ismbbkana_l"
  - "ismbbkana"
  - "_ismbbkana"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbbkana_l 함수"
  - "_ismbbkana 함수"
  - "ismbbkana 함수"
  - "ismbbkana_l 함수"
ms.assetid: 64d4eb4a-205a-40ef-be35-ff9d77fabbaf
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _ismbbkana, _ismbbkana_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가타카나 기호에 대한 테스트이며 코드 페이지 932만 해당됩니다.  
  
## 구문  
  
```  
int _ismbbkana(  
   unsigned int c   
);  
int _ismbbkana_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_ismbbkana`는 정수 `c`가 가타카나 기호인 경우 0이 아닌 값을 반환하고 그렇지 않은 경우 0을 반환합니다.`_ismbbkana`는 로캘 종속 문자 정보에 대한 현재 로캘을 사용합니다.`_ismbbkana_l`은 전달된 로캘 개체를 사용한다는 점을 제외하고 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ismbbkana`|\<mbctype.h\>|  
|`_ismbbkana_l`|\<mbctype.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)