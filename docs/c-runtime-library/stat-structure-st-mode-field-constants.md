---
title: "_stat 구조체 st_mode 필드 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "S_IFCHR"
  - "S_IFDIR"
  - "_S_IWRITE"
  - "S_IFMT"
  - "_S_IFDIR"
  - "_S_IREAD"
  - "S_IEXEC"
  - "_S_IEXEC"
  - "_S_IFMT"
  - "S_IWRITE"
  - "S_IFREG"
  - "S_IREAD"
  - "_S_IFCHR"
  - "_S_IFREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_S_IEXEC 상수"
  - "_S_IFCHR 상수"
  - "_S_IFDIR 상수"
  - "_S_IFMT 상수"
  - "_S_IFREG 상수"
  - "_S_IREAD 상수"
  - "_S_IWRITE 상수"
  - "S_IEXEC 상수"
  - "S_IFCHR 상수"
  - "S_IFDIR 상수"
  - "S_IFMT 상수"
  - "S_IFREG 상수"
  - "S_IREAD 상수"
  - "S_IWRITE 상수"
  - "st_mode 필드 상수"
  - "stat 구조체"
  - "stat 구조체, 상수"
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _stat 구조체 st_mode 필드 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## 설명  
 이러한 상수에 파일 형식을 나타내는 데 사용되는 **st\_mode** 필드는 [\_stat 구조](../c-runtime-library/standard-types.md)입니다.  
  
 비트 마스크 상수는 다음과 같습니다.  
  
|상수|의미|  
|--------|--------|  
|`_S_IFMT`|파일 형식 마스크|  
|`_S_IFDIR`|디렉터리|  
|`_S_IFCHR`|특수 문자 \(이면 장치 설정\)|  
|`_S_IFREG`|기본|  
|`_S_IREAD`|읽기 권한, 소유자|  
|`_S_IWRITE`|쓰기 권한, 소유자|  
|`_S_IEXEC`|사용 권한, 실행 검색 소유자|  
  
## 참고 항목  
 [\_stat, \_wstat 함수](../c-runtime-library/reference/stat-functions.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [표준 형식](../c-runtime-library/standard-types.md)   
 [전역 상수](../c-runtime-library/global-constants.md)