---
title: "_ismbbkprint, _ismbbkprint_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbkprint"
  - "_ismbbkprint_l"
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
  - "_ismbbkprint_l"
  - "ismbbkprint"
  - "_ismbbkprint"
  - "ismbbkprint_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbbkprint 함수"
  - "ismbbkprint_l 함수"
  - "ismbbkprint 함수"
  - "_ismbbkprint_l 함수"
ms.assetid: 8d1d3258-1e34-4365-81ed-97c95de25475
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _ismbbkprint, _ismbbkprint_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

특정 멀티바이트 문자가 문장 부호 기호인지 여부를 결정합니다.  
  
## 구문  
  
```  
int _ismbbkprint(  
   unsigned int c   
);  
int _ismbbkprint_l(  
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
 정수 `c`가 ASCII가 아닌 텍스트 또는 ASCII가 아닌 문장 부호 기호이며 `_ismbbkprint`는 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다. 예를 들어 코드 페이지 932에서만 `_ismbbkprint`는 가타카나 영숫자 또는 가타카나 문장 부호\(범위: 0xA1 – 0xDF\)를 테스트합니다.`_ismbbkprint`는 로캘 종속 문자 설정에 대해 현재 로캘을 사용합니다.`_ismbbkprint_l` 은 전달된 로캘을 사용한다는 점을 제외하고 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ismbbkprint`|\<mbctype.h\>|  
|`_ismbbkprint_l`|\<mbctype.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)