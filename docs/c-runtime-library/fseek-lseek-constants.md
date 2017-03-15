---
title: "fseek, _lseek 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SEEK_END"
  - "SEEK_SET"
  - "SEEK_CUR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SEEK_CUR 상수"
  - "SEEK_END 상수"
  - "SEEK_SET 상수"
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fseek, _lseek 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <stdio.h>  
  
```  
  
## 설명  
 *원래* 인수는 초기 위치를 지정하고 다음 매니페스트 상수들의 하나가 될 수 있습니다.  
  
|상수|의미|  
|--------|--------|  
|`SEEK_END`|파일의 끝|  
|`SEEK_CUR`|파일 포인터의 현재 위치|  
|`SEEK_SET`|파일의 시작 부분|  
  
## 참고 항목  
 [fseek, \_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [전역 상수](../c-runtime-library/global-constants.md)