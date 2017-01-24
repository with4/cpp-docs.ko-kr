---
title: "도구 설명을 사용하도록 설정 | Microsoft Docs"
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
  - "도구 설명을 사용하도록 설정"
  - "도구 설명 초기화"
  - "도구 설명[C++], 사용"
  - "도구 설명[C++], 초기화"
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 도구 설명을 사용하도록 설정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

창의 \(예: 폼 뷰나 대화 상자의 컨트롤\) 자식 컨트롤에 대한 도구 설명 지원을 가능 합니다.  
  
### 창의 자식 컨트롤에 도구 설명을 활성화 하려면  
  
1.  도구 설명을 제공하려는 창에 대해 `EnableToolTips` 를 호출하십시오.  
  
2.  [TTN\_NEEDTEXT notification](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) 처리기에서 각 컨트롤에 대해 문자열을 제공하십시오.  \(예를 들어, 폼 뷰 클래스\) 자식 컨트롤이 포함 된 창의 메시지 맵에 처리기입니다.  이 처리기는 컨트롤을 식별하고 도구 설명 컨트롤에 사용되는 텍스트를 지정하는 **pszText** 를 설정하는 함수를 호출합니다.  
  
## 참고 항목  
 [CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)