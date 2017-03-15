---
title: "대화 상자 만들기 및 표시 | Microsoft Docs"
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
  - "MFC 대화 상자, 만들기"
  - "MFC 대화 상자, 표시"
  - "모달 대화 상자, 만들기"
  - "모덜리스 대화 상자, 만들기"
  - "대화 상자 열기"
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 대화 상자 만들기 및 표시
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 단계의 연산이 있는 대화 개체를 만듭니다.  먼저, 대화 개체를 생성한 다음, 대화 창을 만듭니다.  모델과 모델이 없는 대화 상자들은 그들을 보여주고 만드는 과정에서 차이가 있습니다.  다음 표 목룍은 어떻게 모델과 모델이 없는 대화상자들이 일반적으로 생성되고 표시되는지 보여줍니다.  
  
### 대화 상자 만들기  
  
|대화 형식|대화상자를 만드는 방법|  
|-----------|------------------|  
|[Modeless](../mfc/creating-modeless-dialog-boxes.md)|`CDialog` 를 구성한다음, **Create** 멤버 함수를 호출합니다.|  
|[Modal](../mfc/creating-modal-dialog-boxes.md)|`CDialog` 를 구성한 다음, `DoModal` 멤버 함수를 호출합니다.|  
  
 만일 원하고, 할 수 있다면, 대화 상자 템플릿 리소스를 사용해 생성하는 대신 [in\-memory dialog template](../mfc/using-a-dialog-template-in-memory.md) 으로부터 대화상자를 생성할 수 있습니다.  여기에서 다루는 내용은 다음과 같은 내용입니다.  
  
## 참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)