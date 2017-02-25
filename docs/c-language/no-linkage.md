---
title: "링크 없음 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "링크[C++], 없음"
  - "링크 없음"
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 링크 없음
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

블록 내의 식별자 선언에 `extern` 저장소 클래스 지정자가 포함되어 있지 않은 경우 식별자가 링크를 포함하지 않고 함수에 대해 고유한 것입니다.  
  
 다음 식별자에는 링크가 없습니다.  
  
-   개체 또는 함수 이외의 항목으로 선언된 식별자  
  
-   함수 매개 변수로 선언된 식별자  
  
-   `extern` 저장소 클래스 지정자 없이 선언된 개체에 대한 블록 범위 식별자  
  
 식별자에 링크가 없는 경우 동일한 범위 수준에서 선언자 또는 형식 지정자에 동일한 이름을 다시 선언하면 기호 재정의 오류가 발생합니다.  
  
## 참고 항목  
 [extern을 사용하여 링크 지정](../cpp/using-extern-to-specify-linkage.md)