---
title: "stdin, stdout, stderr | Microsoft Docs"
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
  - "stdin"
  - "stderr"
  - "stdout"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "표준 오류 스트림"
  - "표준 입력 스트림"
  - "표준 출력 스트림"
  - "stderr 함수"
  - "stdin 함수"
  - "stdout 함수"
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# stdin, stdout, stderr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## 설명  
 오류 출력과 입력, 출력에 대한 표준 스트림이 있습니다.  
  
 기본적으로, 표준 입력은 표준 출력과 표준 에러가 화면에 출력되는 동안, 키보드로부터 읽혀집니다.  
  
 다음 스트림 포인터들은 표준 스트림을 액세스하는데 사용할 수 있습니다.  
  
|포인터|스트림|  
|---------|---------|  
|`stdin`|표준 입력|  
|**stdout**|표준 출력|  
|`stderr`|표준 오류|  
  
 이러한 포인터들은 함수에 대한 매개변수로써 사용될 수 있습니다.  **getchar** 와 `putchar`와 같은 일부 함수들은 자동적으로 `stdin` 과 **stdout** 을 사용합니다.  
  
 이러한 포인터는 상수들이고 새로운 값이 할당될 수 없습니다.  `freopen` 함수는 다른 장치들 또는 디스크 파일들에 대한 스트림을 리디렉션하기 위해 사용될 수 있습니다.  운영 체제는 명령레벨에서 프로그램의 표준 입력과 출력을 리디렉션 할 수 있도록 합니다.  
  
## 참고 항목  
 [스트림 I\/O](../c-runtime-library/stream-i-o.md)   
 [전역 상수](../c-runtime-library/global-constants.md)