---
title: "When Do I Need to Call AtlAxWinTerm? | Microsoft Docs"
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
  - "AtlAxWinTerm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinTerm method"
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: 12
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# When Do I Need to Call AtlAxWinTerm?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinTerm](../Topic/AtlAxWinTerm.md) 등록 취소를  **"AtlAxWin80"** 창 클래스입니다.  \(더 이상 호스트 창을 만드는 데 필요한 경우\) 모든 기존 호스트 창을 소멸 한 후이 함수를 호출 해야 합니다.  이 함수를 호출 하지 않으면 프로세스가 종료 될 때 창 클래스가 자동으로 등록 됩니다.  
  
## 참고 항목  
 [When Do I Need to Call AtlAxWinInit?](../atl/when-do-i-need-to-call-atlaxwininit-q.md)   
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)