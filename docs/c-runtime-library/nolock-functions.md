---
title: "_nolock 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_nolock 함수"
  - "nolock 함수"
ms.assetid: 7d651d87-38d2-4303-9897-fdb5f7a3e899
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _nolock 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 함수들은 어떤 잠금도 수행 하지 않습니다.  최고의 성능을 필요로 하는 사용자들에게 제공 됩니다.  자세한 내용은 [다중 스레드 라이브러리 성능](../c-runtime-library/multithreaded-libraries-performance.md)을 참조하십시오.  
  
 단일 스레드 프로그램이나 또는 자체 잠금이 있는 프로그램에만 \_nolock 함수를 사용 합니다.  
  
 [\_fclose\_nolock](../c-runtime-library/reference/fclose-nolock.md)  
  
 [\_fflush\_nolock](../c-runtime-library/reference/fflush-nolock.md)  
  
 [\_fgetc\_nolock, \_fgetwc\_nolock](../c-runtime-library/reference/fgetc-nolock-fgetwc-nolock.md)  
  
 [\_fread\_nolock](../c-runtime-library/reference/fread-nolock.md)  
  
 [\_fseek\_nolock, \_fseeki64\_nolock](../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)  
  
 [\_ftell\_nolock, \_ftelli64\_nolock](../c-runtime-library/reference/ftell-nolock-ftelli64-nolock.md)  
  
 [\_fwrite\_nolock](../c-runtime-library/reference/fwrite-nolock.md)  
  
 [\_getc\_nolock, \_getwc\_nolock](../c-runtime-library/reference/getc-nolock-getwc-nolock.md)  
  
 [\_getch\_nolock, \_getwch\_nolock](../c-runtime-library/reference/getch-nolock-getwch-nolock.md)  
  
 [\_getchar\_nolock, \_getwchar\_nolock](../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md)  
  
 [\_getche\_nolock, \_getwche\_nolock](../c-runtime-library/reference/getche-nolock-getwche-nolock.md)  
  
 [\_getdcwd\_nolock, \_wgetdcwd\_nolock](../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)  
  
 [\_putc\_nolock, \_putwc\_nolock](../c-runtime-library/reference/putc-nolock-putwc-nolock.md)  
  
 [\_putch\_nolock, \_putwch\_nolock](../c-runtime-library/reference/putch-nolock-putwch-nolock.md)  
  
 [\_putchar\_nolock, \_putwchar\_nolock](../c-runtime-library/reference/putchar-nolock-putwchar-nolock.md)  
  
 [\_ungetc\_nolock, \_ungetwc\_nolock](../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md)  
  
 [\_ungetc\_nolock, \_ungetwc\_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)  
  
## 참고 항목  
 [입력 및 출력](../c-runtime-library/input-and-output.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)