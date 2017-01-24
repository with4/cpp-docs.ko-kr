---
title: "srand | Microsoft Docs"
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
  - "srand"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "srand"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "숫자, 의사 난수"
  - "숫자, 난수"
  - "의사 난수"
  - "난수, 생성"
  - "임의의 시작점"
  - "임의의 시작점, 설정"
  - "srand 함수"
  - "시작점"
  - "시작점, 임의의 시작점 설정"
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# srand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

의사 난수 생성기에 대한 시작 시드 값을 설정합니다.  
  
## 구문  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### 매개 변수  
 `seed`  
 의사 난수 생성에 대한 시드  
  
## 설명  
 `srand` 함수는 현재 스레드의 일련의 의사 난수 정수를 생성 하기 위한 시작점을 설정 합니다.  호출 시퀀스가 동일한 결과 만드는 생성자를 초기화 하기 위해, `srand` 작동을 호출하고  `seed` 인수와 똑같은 이름을 다시 사용합니다.  `seed` 에 대한 다른 값은 생성자를 난수 시퀀스의 다른 시작 지점으로 설정합니다.  `rand` 생성 된 난수를 검색 합니다.  `rand` 를 `srand` 가  `srand` 와 1로 전달된 `seed` 를 호출하는 같은 시퀀서를 호출하기 전에 호출합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`srand`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [rand](../../c-runtime-library/reference/rand.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Random 클래스](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)