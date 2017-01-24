---
title: "CObject에서 클래스를 파생시키는 비용 | Microsoft Docs"
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
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject 클래스, 파생 클래스 오버헤드"
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObject에서 클래스를 파생시키는 비용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The overhead in deriving from class [CObject](../mfc/reference/cobject-class.md) is minimal.  Your derived class inherits only four virtual functions and a single [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) object.  
  
## 참고 항목  
 [CObject 클래스: 질문과 대답](../mfc/cobject-class-frequently-asked-questions.md)