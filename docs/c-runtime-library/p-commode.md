---
title: "__p__commode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__p__commode"
apilocation: 
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__p__commode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__p__commode"
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# __p__commode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파일 I\/O 연산자에 대한 기본 *file commit mode* 를 지정하는 `_commode` 전역 변수를 가르키는 포인터 입니다.  
  
## 구문  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## 반환 값  
 `_commode` 전역 변수에 대한 포인터 입니다.  
  
## 설명  
 `__p__commode`는 함수 내부 에서만 사용 되며 사용자 코드에서 호출할 수 없습니다.  
  
 중요 한 데이터가 디스크에 기록 되면 파일 커밋 모드는 지정합니다.  자세한 내용은 [fflush](../c-runtime-library/reference/fflush.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_\_p\_\_commode|internal.h|