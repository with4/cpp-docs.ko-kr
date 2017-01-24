---
title: "단순한 읽기 전용 공급자의 기능 향상 | Microsoft Docs"
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
  - "IRowsetLocate 클래스"
  - "IRowsetLocate 클래스, OLE DB 템플릿 공급자에 추가"
  - "읽기 전용 공급자[C++]"
  - "단순한 읽기 전용 공급자[C++]"
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 단순한 읽기 전용 공급자의 기능 향상
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 단원에서는 이전 단원에서 만든 [단순한 읽기 전용 공급자](../../data/oledb/implementing-the-simple-read-only-provider.md)의 기능을 향상시키는 방법을 보여 줍니다.  `IRowsetLocateImpl`은 `IRowsetLocate` 인터페이스를 구현하고 책갈피 지원을 추가합니다.  
  
 작동하는 공급자를 만들면 공급자의 기능을 향상시켜 공급자 업데이트를 만들거나, 트랜잭션을 처리하도록 하거나, 행 페치 알고리즘의 성능을 향상시킬 수 있습니다.  대부분 공급자 기능을 향상시키기 위해 기존 COM 개체에 인터페이스를 추가합니다.  
  
 다음 항목의 예제에서는 `CAgentRowset`에 `IRowsetLocate` 인터페이스를 추가하여 행 페치 메커니즘을 향상시킵니다.  이 항목을 통해 다음 작업에 대한 방법을 알 수 있습니다.  
  
-   [IRowsetLocate에서 RMyProviderRowset 상속](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)  
  
-   [소비자에게 반환할 열을 동적으로 결정](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)  
  
## 참고 항목  
 [단순한 읽기 전용 공급자 만들기](../../data/oledb/creating-a-simple-read-only-provider.md)