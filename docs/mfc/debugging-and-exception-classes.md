---
title: "디버깅 및 예외 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "디버깅[MFC], 디버깅 클래스"
  - "디버깅[MFC], 예외 클래스"
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 디버깅 및 예외 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이들 클래스는 동적 메모리 할당을 디버깅하는 것과 예외 정보를 예외가 발생한 함수에서부터 예외가 탐지된 함수로 전달하는 것을 지원합니다.  
  
 개발하는 동안 디버깅하는 것을 돕기 위해서, [Debugging MFC Applications](../Topic/MFC%20Debugging%20Techniques.md)에 설명된 대로 클래스 [CDumpContext](../mfc/reference/cdumpcontext-class.md) 및 [CMemoryState](../mfc/reference/cmemorystate-structure.md)을 사용하세요.  [Accessing Run\-Time Class Information](../mfc/accessing-run-time-class-information.md) 문서에서 설명한 대로 실행시 모든 개체 클래스를 결정하기 위해 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)를 사용하세요.  특정 클래스를 개체를 동적으로 만들기 위해서 framework는 `CRuntimeClass`를 사용합니다.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)