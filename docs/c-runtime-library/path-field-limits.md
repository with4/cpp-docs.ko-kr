---
title: "경로 필드 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_MAX_EXT"
  - "_MAX_DIR"
  - "_MAX_PATH"
  - "_MAX_FNAME"
  - "_MAX_DRIVE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_MAX_DIR 상수"
  - "_MAX_DRIVE 상수"
  - "_MAX_EXT 상수"
  - "_MAX_FNAME 상수"
  - "_MAX_PATH 상수"
  - "MAX_DIR 상수"
  - "MAX_DRIVE 상수"
  - "MAX_EXT 상수"
  - "MAX_FNAME 상수"
  - "경로 필드 상수"
  - "경로, 최대 제한"
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 경로 필드 제한
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
#include <stdlib.h>  
```  
  
## 설명  
 이러한 상수는 경로 및 경로 내에서 개별 필드의 최대 길이입니다.  
  
|상수|의미|  
|--------|--------|  
|`_MAX_DIR`|디렉터리 구성 요소의 최대 길이입니다.|  
|`_MAX_DRIVE`|드라이브 구성 요소의 최대 길이입니다.|  
|`_MAX_EXT`|확장 구성 요소의 최대 길이입니다.|  
|`_MAX_FNAME`|파일 이름 구성 요소의 최대 길이입니다.|  
|`_MAX_PATH`|전체 경로의 최대 길이입니다.|  
  
> [!NOTE]
>  C 런타임은 길이 32768 문자까지 최대 경로 길이를 지원 하지만 운영 체제에서는 특히 파일 시스템에서 이러한 긴 경로를 지원 하도록 합니다.  필드의 합계는 FAT32 파일 시스템를 사용한 전체 이전 버전 호환성에 대해 `_MAX_PATH` 를 초과할 수 없습니다.  [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)], [!INCLUDE[WinXpFamily](../c-runtime-library/includes/winxpfamily_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], 및 Windows Vista NTFS 파일 시스템은 Unicode APIs 를 사용하는 경우 32768 문자 길이 까지 경로를 지원합니다.  긴 경로 이름을 사용 하는 경우 \\\\?\\ 문자를 사용하여 경로를 앞에 붙이고 런타임 함수의 유니코드 버전을 사용 합니다.  
  
## 참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)