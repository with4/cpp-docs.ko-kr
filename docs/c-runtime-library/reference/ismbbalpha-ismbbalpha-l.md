---
title: "_ismbbalpha, _ismbbalpha_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbalpha"
  - "_ismbbalpha_l"
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
  - "ismbbalpha"
  - "ismbbalpha_l"
  - "_ismbbalpha"
  - "_ismbbalpha_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ismbbalpha 함수"
  - "ismbbalpha_l 함수"
  - "_ismbbalpha 함수"
  - "_ismbbalpha_l 함수"
ms.assetid: 8e54cb92-fc2b-41f5-8ab4-b22ac8aa9ad0
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbbalpha, _ismbbalpha_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 멀티바이트 문자가 영문자인지 여부를 확인합니다.  
  
## 구문  
  
```  
int _ismbbalpha(  
   unsigned int c   
);  
int _ismbbalpha_l(  
   unsigned int c   
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 식이 다음과 같을 경우 `_ismbbalpha`은 0이 아닌 값을 반환합니다.  
  
```  
isalpha || _ismbbkalnum  
```  
  
 `c`에 대해 0이 아니며, 그렇지 않은 경우 0입니다.`_ismbbalpha`는 모든 로캘 종속 문자 설정에 대한 현재 로캘을 사용합니다.`_ismbbalpha_l`은 전달된 로캘을 사용한다는 점을 제외하고 동일합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ismbbalpha`|\<mbctype.h\>|  
|`_ismbbalpha_l`|\<mbctype.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)