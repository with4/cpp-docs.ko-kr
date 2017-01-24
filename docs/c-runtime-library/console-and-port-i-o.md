---
title: "콘솔 및 포트 I/O | Microsoft Docs"
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
  - "c.io"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "I/O[CRT], 콘솔"
  - "I/O[CRT], 포트"
  - "I/O 루틴, 콘솔 및 포트 I/O"
  - "포트, I/O 루틴"
  - "루틴"
  - "루틴, 콘솔 및 포트 I/O"
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 콘솔 및 포트 I/O
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이러한 루틴은 콘솔이나 지정된 포트에 읽고 씁니다.  콘솔 I\/O 루틴은 I\/O 스트림 또는 하위 수준 I\/O 라이브러리 루틴을 사용 하여 호환 되지 않습니다.  콘솔이나 포트를 열거 나 I\/O가 수행되기 전에 종료 할 필요가 없습니다, ​​그래서이 범주에 열고 닫는 루틴이 없습니다.  윈도우 운영 체제에서, 이들 함수의 출력은 항상 콘솔에 관한 것이며 리디렉션 될 수 없습니다.  
  
### 콘솔 및 포트 I\/O 루틴  
  
|루틴|기능|  
|--------|--------|  
|[\_cgets, \_cgetws](../c-runtime-library/cgets-cgetws.md), [\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|콘솔에서 문자열 읽기|  
|[\_cprintf, \_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md),[\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|콘솔에 서식이 지정된 데이터를 씁니다.|  
|[\_cputs](../c-runtime-library/reference/cputs-cputws.md)|콘솔에 문자열 쓰기|  
|[\_cscanf, \_cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md),[\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|콘솔에서 서식이 지정된 데이터를 읽습니다.|  
|[\_getch, \_getwch](../c-runtime-library/reference/getch-getwch.md)|콘솔에서 문자를 읽습니다.|  
|[\_getche, \_getwche](../c-runtime-library/reference/getch-getwch.md)|콘솔에서 문자를 읽고 표시합니다.|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|지정 된 I\/O 포트에서 1 바이트를 읽습니다.|  
|[\_inpd](../c-runtime-library/inp-inpw-inpd.md)|지정 된 I\/O 포트에서 이중 단어를 읽습니다.|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|지정 된 I\/O 포트에서 2 바이트 단어를 읽습니다.|  
|[\_kbhit](../c-runtime-library/reference/kbhit.md)|콘솔에서 읽기를 시도하기 전에 사용하여 콘솔에서 키 입력을 확인합니다.|  
|[\_outp](../c-runtime-library/outp-outpw-outpd.md)|지정 된 I\/O 포트에 1 바이트를 씁니다.|  
|[\_outpd](../c-runtime-library/outp-outpw-outpd.md)|지정 된 I\/O 포트에 이중 단어를 씁니다.|  
|[\_outpw](../c-runtime-library/outp-outpw-outpd.md)|지정 된 I\/O 포트에 단어를 씁니다.|  
|[\_putch, \_putwch](../c-runtime-library/reference/putch-putwch.md)|콘솔에 문자를 씁니다.|  
|[\_ungetch, \_ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|"Unget" 의 마지막 문자는 콘솔에서 읽기 때문에 콘솔에서 읽은 다음 문자입니다.|  
  
## 참고 항목  
 [입력 및 출력](../c-runtime-library/input-and-output.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)