---
title: "파일 특성 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A_HIDDEN"
  - "_A_NORMAL"
  - "_A_SUBDIR"
  - "_A_RDONLY"
  - "A_NORMAL"
  - "A_SUBDIR"
  - "_A_SYSTEM"
  - "c.constants.file"
  - "_A_HIDDEN"
  - "A_RDONLY"
  - "_A_ARCH"
  - "A_ARCH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_A_ARCH 상수"
  - "_A_HIDDEN 상수"
  - "_A_NORMAL 상수"
  - "_A_RDONLY 상수"
  - "_A_SUBDIR 상수"
  - "_A_SYSTEM 상수"
  - "상수[C++], 파일 특성"
  - "파일 특성 상수[C++]"
  - "파일[C++], 파일 특성 상수"
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 파일 특성 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <io.h>  
```  
  
## 설명  
 이러한 상수들은 함수에 의해 지정된 파일 또는 디텍터리의 현재 속성을 지정합니다.  
  
 다음의 매니페스트 상수가 속성을 대표합니다.  
  
 `_A_ARCH`  
 \-Archive  백업 커맨드에 의해 파일이 변경되거나 삭제될 시간을 설정합니다.  값: 0x20  
  
 `_A_HIDDEN`  
 숨김 파일  \/AH 옵션이 사용되지 않는다면, 일반적으로 DIR 명령으로 볼 수 없습니다.  이 속성을 가진 파일뿐만 아니라 일반 파일에 대한 정보도 반환합니다.  값: 0x02  
  
 `_A_NORMAL`  
 정상입니다.  파일을 제한 없이 읽거나 쓸 수 있습니다.  값: 0x00  
  
 `_A_RDONLY`  
 읽기 전용.  파일을 쓰기 위해 열 수 없고 같은 이름을 가진 파일을 만들 수 없습니다.  값: 0x01  
  
 `_A_SUBDIR`  
 하위 디렉터리  값: 0x10  
  
 `_A_SYSTEM`  
 시스템 파일입니다.  \/AH 옵션이 사용되지 않는다면, 일반적으로 DIR 명령으로 볼 수 없습니다.  값: 0x04  
  
 여러 상수들은 OR 연산자 \(l\)와 결합될 수 있습니다.  
  
## 참고 항목  
 [파일 이름 검색 함수](../c-runtime-library/filename-search-functions.md)   
 [전역 상수](../c-runtime-library/global-constants.md)