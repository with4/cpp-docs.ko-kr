---
title: "CObject에서 새 클래스를 파생시켜야 합니까? | Microsoft Docs"
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
  - "CObject 클래스, 사용 시기"
  - "파생 클래스, CObject에서"
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObject에서 새 클래스를 파생시켜야 합니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

아니요, 없습니다.  
  
 직렬화 또는 동적 creatability 등을 제공 하는 기능을 할 때  [CObject](../mfc/reference/cobject-class.md)에서 클래스가 파생됩니다.  많은 데이터 클래스 파일로 직렬화 할 필요가 있기 때문에, `CObject`에서 그들을 파생하는 것이 좋습니다   `CObject` 에서 파생 된 클래스의 예는 [Scribble 샘플](../top/visual-cpp-samples.md)을 참조하십시오.  
  
## 참고 항목  
 [CObject 클래스: 질문과 대답](../mfc/cobject-class-frequently-asked-questions.md)