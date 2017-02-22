---
title: "EOF, WEOF | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EOF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EOF 함수"
  - "WEOF 함수"
  - "파일의 끝"
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# EOF, WEOF
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <stdio.h>  
```  
  
## 설명  
 파일의 끝\(또는 경우에 따라서 오류\)가 발견되면, I\/O 루틴에 의해 EOF가 반환됩니다.  
  
 WEOF 는 **wint\_t** 형식의 반환값을 넘겨주고 와이드 스트림의 끝을 사용하거나 오류 조건을 보고합니다.  
  
## 참고 항목  
 [putc, putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../c-runtime-library/reference/fflush.md)   
 [fclose, \_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [\_putch, \_putwch](../c-runtime-library/reference/putch-putwch.md)   
 [isascii, \_\_isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [전역 상수](../c-runtime-library/global-constants.md)