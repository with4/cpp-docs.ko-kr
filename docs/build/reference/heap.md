---
title: "/HEAP | Microsoft Docs"
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
  - "/heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "힙 할당, 힙 크기 설정"
  - "HEAP editbin 옵션"
  - "-HEAP editbin 옵션"
  - "/HEAP editbin 옵션"
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /HEAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙 크기를 바이트 단위로 설정합니다.  이 옵션은 실행 파일에만 적용 됩니다.  
  
```  
  
/HEAP:  
reserve[,commit]  
  
```  
  
## 설명  
 `reserve` 인수는 가상 메모리에서 전체 힙 할당을 지정합니다.  기본 힙 크기는 1MB입니다.  [EDITBIN 참조](../../build/reference/editbin-reference.md)그러면 링커에서는 지정된 값을 가장 가까운 4바이트 단위 값으로 반올림합니다.  
  
 선택적인 `commit` 인수는 운영 체제에서 해석됩니다.  Windows 운영 체제에서 힙을 확장 해야 하는 경우 할당 하려면 추가 메모리 양과 초기에 할당할 실제 메모리 양을 지정 합니다.  커밋된 가상 메모리는 페이징 파일에 공간을 예약합니다.  높은  `commit`  값을 사용 하면 메모리를 할당할 수 작은 응용 프로그램에 더 많은 힙 공간이 필요할 수 있지만 메모리 요구량과 응용 프로그램 시작 시간 때 종종 시스템입니다.  `commit`의 값은 `reserve`의 값보다 작거나 같아야 합니다.  
  
 지정 된  `reserve`  및  `commit`  십진수 나 C 언어 16 진수 또는 8 진수 표기법의 값입니다.  예를 들어, 값이 1 MB 1048576 10 진수 또는 16 진수로 0x100000 또는 8 진수로 04000000 지정할 수 있습니다.  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)