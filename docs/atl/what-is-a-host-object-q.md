---
title: "What Is a Host Object? | Microsoft Docs"
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
  - "host objects"
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# What Is a Host Object?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

호스트 개체를 특정 창에 대 한 ATL에서 제공한 ActiveX 컨트롤 컨테이너를 나타내는 COM 개체가입니다.  호스트 서브 클래스는 컨테이너 컨트롤에 메시지를 반영할 수 있습니다, 필요한 컨테이너 컨트롤에서 사용할 인터페이스를 제공 하 고 노출 개체 창에서  [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) 및  [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) 컨트롤의 환경을 구성할 수 있도록 하는 인터페이스.  
  
 호스트 개체 컨테이너의 앰비언트 속성을 설정할 수 있습니다.  
  
## 참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)