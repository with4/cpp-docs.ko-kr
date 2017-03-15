---
title: "변환 모드 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_O_BINARY"
  - "_O_TEXT"
  - "_O_RAW"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_O_BINARY 상수"
  - "_O_RAW 상수"
  - "_O_TEXT 상수"
  - "O_BINARY 상수"
  - "O_RAW 상수"
  - "O_TEXT 상수"
  - "변환 상수"
  - "변환 모드(파일 I/O)"
  - "변환, 상수"
  - "변환, 모드"
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 변환 모드 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <fcntl.h>  
  
```  
  
## 설명  
 `_O_BINARY` 와 `_O_TEXT` 매니페스트 상수들은 파일들\(`_open` 과 `_sopen`\) 에 대한 좌표 이동 모드 또는 스트림들\(`_setmode`\)에 대한 좌표 이동 모드를 결정합니다.  
  
 허용되는 값은 다음과 같습니다.  
  
 `_O_TEXT`  
 \(변환된\)텍스트 모드에서 파일을 엽니다.  캐리지 리턴\-줄바꿈\(CR\-LF\) 결합은 입력에서 단일 줄 바꿈\(LF\)으로 변환됩니다.  줄 바꿈된 문자는 출력에서 CR\-LF 조합으로 변환됩니다.  또한, CTRL \+ Z는 입력에서 파일 끝 문자로 해석 됩니다.  읽기\/쓰기와 읽기를 위해 파일을 열 때, `fopen` 는 가능하다면 파일의 끝에서 CTRL\+Z에 대해 검사하고 이것을 제거합니다.  `fseek` 및 `ftell`을 사용하여 Ctrl\+Z로 끝나는 파일 내에서 이동하면 파일의 끝 부분에서 `fseek`가 제대로 동작하지 않을 수 있으므로 이 작업을 수행합니다.  
  
 `_O_BINARY`  
 이진 \(변환 되지 않은\) 모드에서 파일을 엽니다.  위의 변환이 억제됩니다.  
  
 `_O_RAW`  
 `_O_BINARY`와 동일합니다.  C 2.0 호환성을 위해 지원됩니다.  
  
 보다 자세한 내용은 [텍스트와 이진 모드 파일 입출력](../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [파일 좌표 이동](../c-runtime-library/file-translation-constants.md) 을 참고하세요.  
  
## 참고 항목  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_pipe](../c-runtime-library/reference/pipe.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_setmode](../c-runtime-library/reference/setmode.md)   
 [전역 상수](../c-runtime-library/global-constants.md)