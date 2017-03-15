---
title: "내부 링크 | Microsoft Docs"
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
  - "내부 링크"
  - "링크[C++], internal"
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 내부 링크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

개체 또는 함수의 파일 범위 식별자 선언에 *storage\-class\-specifier* **static**이 있으면 식별자에 내부 링크가 있고  그렇지 않으면 식별자에 외부 링크가 있습니다.  *storage\-class\-specifier* 비터미널에 대한 설명은 [저장소 클래스](../c-language/c-storage-classes.md)를 참조하십시오.  
  
 변환 단위 안에서 내부 링크가 있는 식별자의 각 인스턴스는 같은 식별자 또는 함수를 나타냅니다.  내부적으로 연결된 식별자는 변환 단위마다 다릅니다.  
  
## 참고 항목  
 [extern을 사용하여 링크 지정](../cpp/using-extern-to-specify-linkage.md)