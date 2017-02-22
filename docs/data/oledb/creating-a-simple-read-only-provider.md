---
title: "단순한 읽기 전용 공급자 만들기 | Microsoft Docs"
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
  - "OLE DB 공급자 템플릿, 공급자 만들기"
  - "OLE DB 공급자, 만들기"
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 단순한 읽기 전용 공급자 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 프로젝트 마법사와 ATL OLE DB 공급자 마법사를 사용하여 OLE DB 공급자를 만들었으면 지원할 다른 기능을 추가할 수 있습니다.  먼저 소비자에게 보낼 데이터 종류와 데이터를 보내는 조건을 검토하여 공급자 디자인을 시작합니다.  특히 명령이나 트랜잭션 및 기타 선택적 개체를 지원해야 하는지를 결정하는 것이 중요합니다.  시작할 때 디자인을 잘 하면 구현과 테스트 속도가 빨라집니다.  
  
 다음 두 장에서 예제가 제공됩니다.  
  
-   첫 번째 장에서는 문자열 쌍을 읽는 [단순한 읽기 전용 공급자 구현](../../data/oledb/implementing-the-simple-read-only-provider.md) 방법을 볼 수 있습니다.  
  
-   두 번째 장에서는 `IRowsetLocate`인터페이스를 추가하여 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md) 방법을 볼 수 있습니다.  
  
## 참고 항목  
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)