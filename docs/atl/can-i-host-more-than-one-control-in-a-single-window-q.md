---
title: "Can I Host More Than One Control in a Single Window? | Microsoft Docs"
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
  - "컨트롤[ATL], hosting multiple"
  - "windows [C++], hosting multiple controls"
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Can I Host More Than One Control in a Single Window?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

단일 ATL 호스트 창에 두 개 이상의 컨트롤을 호스팅할 수 없습니다.  각 호스트 창 \(메시지 리플렉션 및 컨트롤 당 앰비언트 속성을 처리 하는 간단한 메커니즘에 대 한 허용\) 한 번에 정확히 컨트롤 한 개만 보유 하도록 설계 되었습니다.  그러나 단일 창에서 여러 개의 컨트롤을 볼 수 있도록 사용자가 필요한 경우 간단 하 게 다중 호스트 창을 해당 창의 자식으로 만들 수 있습니다.  
  
## 참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)