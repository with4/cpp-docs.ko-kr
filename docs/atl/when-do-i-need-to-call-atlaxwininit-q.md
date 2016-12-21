---
title: "When Do I Need to Call AtlAxWinInit? | Microsoft Docs"
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
  - "AtlAxWinInit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinInit method"
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# When Do I Need to Call AtlAxWinInit?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[AtlAxWinInit](../Topic/AtlAxWinInit.md) 레지스터의  **"AtlAxWin80"** 창 클래스 \(몇 가지 사용자 정의 창 메시지 플러스\) 호스트 창을 만들기 전에이 함수를 호출 해야 하며.  그러나 항상 Api와 클래스를 사용 하 여 호스팅하는 이후이 함수를 명시적으로 호출 하면 없습니다이 함수를 호출 하는 경우가 많습니다.  이 함수를 여러 번 호출에 영향을 미치지가입니다.  자세한 내용은  [ATL 컨트롤 호스팅 API는 무엇입니까?](../atl/what-is-the-atl-control-hosting-api-q.md).  
  
## 참고 항목  
 [When Do I Need to Call AtlAxWinTerm?](../atl/when-do-i-need-to-call-atlaxwinterm-q.md)   
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)