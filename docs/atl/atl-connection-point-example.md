---
title: "ATL Connection Point Example | Microsoft Docs"
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
  - "연결 지점[C++], 예제"
  - "examples [ATL]"
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Connection Point Example
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 예제를 지 원하는 개체  [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 으로 나가는 인터페이스:  
  
 [!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/CPP/atl-connection-point-example_1.h)]  
  
 지정 하는 경우 `IPropertyNotifySink` 송신 인터페이스로 클래스를 사용할 수 있습니다  [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 대신 `IConnectionPointImpl`.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/CPP/atl-connection-point-example_2.h)]  
  
## 참고 항목  
 [연결 지점](../atl/atl-connection-points.md)