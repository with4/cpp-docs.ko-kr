---
title: "/STACK | Microsoft Docs"
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
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STACK editbin 옵션"
  - "STACK editbin 옵션"
  - "-STACK editbin 옵션"
  - "스택, 크기 설정"
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /STACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## 설명  
 이 옵션은 바이트 단위로 스택 크기를 설정하고 10진법 또는 C 언어 표기법으로 인수를 사용합니다.  \/STACK 옵션은 실행 파일에만 적용됩니다.  
  
 *reserve* 인수는 가상 메모리에서 전체 스택 할당을 지정합니다.  EDITBIN은 지정된 값을 4바이트 단위의 가장 가까운 값으로 반올림합니다.  
  
 선택적인 `commit` 인수는 운영 체제에서 해석됩니다.  Windows NT, Windows 95 및 Windows 98에서 `commit`은 한 번에 할당할 실제 메모리 양을 지정합니다.  커밋된 가상 메모리는 페이징 파일에 공간을 예약합니다.  `commit` 값이 크면 응용 프로그램에 더 많은 스택 공간이 필요할 때 시간을 절약할 수 있지만 메모리 요구량과 시작 시간이 늘어날 수 있습니다.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)