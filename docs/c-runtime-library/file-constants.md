---
title: "파일 상수 | Microsoft Docs"
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
  - "_O_EXCL"
  - "_O_RDWR"
  - "_O_APPEND"
  - "_O_RDONLY"
  - "_O_TRUNC"
  - "_O_CREAT"
  - "_O_WRONLY"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_O_APPEND 상수"
  - "_O_CREAT 상수"
  - "_O_EXCL 상수"
  - "_O_RDONLY 상수"
  - "_O_RDWR 상수"
  - "_O_TRUNC 상수"
  - "_O_WRONLY 상수"
  - "O_APPEND 상수"
  - "O_CREAT 상수"
  - "O_EXCL 상수"
  - "O_RDONLY 상수"
  - "O_RDWR 상수"
  - "O_TRUNC 상수"
  - "O_WRONLY 상수"
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 파일 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <fcntl.h>  
  
```  
  
## 설명  
 하나이상의 이러한 상수로부터 현성된 정수 표현은 허용된 읽기 또는 쓰기 작업의 형식을 결정합니다.  이것은 변환 모드 상수를 사용하여 하나 이상의 상수를 조합하여 형성됩니다.  
  
 파일 상수는 다음과 같습니다:  
  
 `_O_APPEND`  
 매번 쓰기 작업을 하기 전에 파일의 끝에 파일 포인터를 다시 설정합니다.  
  
 `_O_CREAT`  
 쓰기에 대한 새 파일을 만들고 엽니다: 만일 기존의 파일이 *파일이름* 이 존재하여 중복된 경우, 이것은 적용되지 않습니다.  
  
 `_O_EXCL`  
 *filename* 에 의해 지정된 파일이 존재하면 에러 값을 반환합니다.  `_O_CREAT` 와 함께 사용할 때만 적용 됩니다.  
  
 `_O_RDONLY`  
 파일을 읽기 전용으로 엽니다; 이 플래그를 지정된 경우, `_O_RDWR` 와 `_O_WRONLY` 가 아니라면 제공될 수 있습니다.  
  
 `_O_RDWR`  
 파일을 읽기와 쓰기 모두 가능하게 엽니다; 만일 이 플래그를 지정한 경우, `_O_RDONLY` 와 `_O_WRONLY` 가 아니라면 제공 될 수 있습니다.  
  
 `_O_TRUNC`  
 길이 0으로 기존 파일을 자르고 엽니다; 파일은 쓰기 권한을 가져야 합니다.  파일의 내용이 삭제됩니다.  이 플래그를 준 경우, `_O_RDONLY` 를 지정할 수 없습니다.  
  
 `_O_WRONLY`  
 쓰기 전용 파일입니다; 이 플래그를 지정된 경우, `_O_RDONLY` 와 `_O_RDWR` 가 아니라면 제공될 수 있습니다.  
  
## 참고 항목  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [전역 상수](../c-runtime-library/global-constants.md)