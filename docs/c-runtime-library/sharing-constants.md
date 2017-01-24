---
title: "상수 공유 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SH_DENYNO"
  - "_SH_DENYRD"
  - "_SH_DENYRW"
  - "_SH_DENYWR"
  - "_SH_COMPAT"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_SH_COMPAT 상수"
  - "_SH_DENYNO 상수"
  - "_SH_DENYRD 상수"
  - "_SH_DENYRW 상수"
  - "_SH_DENYWR 상수"
  - "SH_COMPAT 상수"
  - "SH_DENYNO 상수"
  - "SH_DENYRD 상수"
  - "SH_DENYRW 상수"
  - "SH_DENYWR 상수"
  - "공유 상수"
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 상수 공유
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파일 공유모드에 대한 상수들.  
  
## 구문  
  
```  
  
#include <share.h>  
  
```  
  
## 설명  
 *shflag* 하나 이상의 상수로 구성된 인수는 공유모드를 결정합니다.  이것은 *oflag* 인수들과 결합될 수 있습니다.\([파일 상수](../c-runtime-library/file-constants.md)를 참고하세요\)  
  
 다음 표를 통해 상수들과 그들의 의미를 알 수 있습니다.  
  
|상수|의미|  
|--------|--------|  
|`_SH_DENYRW`|파일에 대한 읽기 및 쓰기 액세스를 거부합니다.|  
|`_SH_DENYWR`|파일에 대한 쓰기 액세스를 거부합니다.|  
|`_SH_DENYRD`|파일에 대한 읽기 액세스를 거부합니다.|  
|`_SH_DENYNO`|읽기 및 쓰기 액세스 권한|  
|`_SH_SECURE`|안전 모드를 설정합니다. \(쓰기에 대한 전용 액세스, 읽기 공유\).|  
  
## 참고 항목  
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [전역 상수](../c-runtime-library/global-constants.md)