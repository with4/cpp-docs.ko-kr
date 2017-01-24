---
title: "Design Principles for Collection and Enumerator Interfaces | Microsoft Docs"
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
  - "collection interfaces"
  - "enumerator interfaces"
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Design Principles for Collection and Enumerator Interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 인터페이스 형식은 다른 디자인 원리입니다.  
  
-   컬렉션 인터페이스를 제공 합니다.  *임의의* 액세스는  *단일* 컬렉션을 통해 항목에에서는  **항목** 메서드를이 수를 통해 컬렉션에 있는 항목 수를 검색 하는 클라이언트는  **수** 속성을 종종 클라이언트 항목 추가 및 제거를 허용 하 고.  
  
-   열거자 인터페이스 제공  *직렬* 액세스  *여러* 항목의 컬렉션 \(열거자 항목 반환 중지 될 때까지\) 컬렉션에 있는 항목 수를 찾으려면 클라이언트 허용 하지 않는 및 모든 방법 항목 추가 또는 제거를 제공 하지 않습니다.  
  
 각 인터페이스의 형식에 액세스 하는 컬렉션의 요소를 제공 하는 다른 역할을 수행 합니다.  
  
## 참고 항목  
 [컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)