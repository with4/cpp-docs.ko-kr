---
title: "모달 대화 상자 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
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
  - "MFC 대화 상자, 모달"
  - "모달 대화 상자, 만들기"
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 모달 대화 상자 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모달 대화 상자를 만들려면 [CDialog](../mfc/reference/cdialog-class.md)에서 선언된 두 public 생성자를 호출합니다.   그런 다음 대화 상자 개체의  [DoModal](../Topic/CDialog::DoModal.md) 멤버 함수를 호출하여 대화 상자를 표시하고 사용자가 확인 될 때까지 상호 작용을 관리 또는 취소합니다.  이  `DoModal` 를 통한 관리는 대화 상자 모달이 만드는 것입니다.  모달 대화 상자에 대해  `DoModal` 는 대화 리소스를 로드합니다.  
  
## 참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)