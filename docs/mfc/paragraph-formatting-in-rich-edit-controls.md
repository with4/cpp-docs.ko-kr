---
title: "Rich Edit 컨트롤의 단락 서식 지정 | Microsoft Docs"
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
  - "CRichEditCtrl 클래스, 단락 서식 지정"
  - "서식 지정[C++], 단락"
  - "CRichEditCtrl의 단락 서식 지정"
  - "rich edit 컨트롤, 단락 서식 지정"
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Rich Edit 컨트롤의 단락 서식 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

절 형식을 지정하고 서식 정보를 검색하기 위해서 rich 편집 컨트롤\([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\)의 멤버 함수를 사용할 수 있습니다.  절 서식 특성은 맞춤, 탭, 들여쓰기 및 번호 붙이기를 포함합니다.  
  
 [SetParaFormat](../Topic/CRichEditCtrl::SetParaFormat.md) 멤버 함수를 사용한 절 서식을 적용할 수 있습니다.  선택된 텍스트의 현재 절 서식을 확인하기 위하여, [GetParaFormat](../Topic/CRichEditCtrl::GetParaFormat.md) 멤버 함수를 사용하세요.  [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940)구조체는 절 특성을 지정하기 위해 이러한 멤버 함수를 사용하여 사용됩니다.  **PARAFORMAT**의 중요한 멤버 중 하나는 **dwMask**입니다.  `SetParaFormat`에서, **dwMask**는 이 함수 호출에 의하여 설정될 절 특성을 지정합니다.  `GetParaFormat`는 선택 영역에서 첫번째 절의 특성을 알립니다. **dwMask**는 선택 영역 전부에서 일관된 특성을 지정합니다.  
  
## 참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)