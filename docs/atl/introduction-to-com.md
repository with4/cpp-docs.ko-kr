---
title: "COM 소개 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM"
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# COM 소개
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM는 OLE 및 ActiveX 컨트롤 내장 된 기본 "개체 모델"입니다.  COM 개체가 다른 구성 요소와 호스트 응용 프로그램의 기능을 노출할 수 있습니다.  이 개체를 표시 하는 방법 및이 노출이 전체 프로세스와 네트워크 작동 방식을 모두 정의 합니다.  또한 COM 개체의 수명 주기를 정의합니다.  
  
 이러한 개념에 COM 기본입니다.  
  
-   [인터페이스](../atl/interfaces-atl.md) \-개체 노출 기능을 통해 메커니즘.  
  
-   [IUnknown](../atl/iunknown.md) \-기본 인터페이스에서 다른 모든 기반으로 합니다.  참조 횟수 및 인터페이스 쿼리 메커니즘을 실행 하는 COM을 통해 구현  
  
-   [참조 횟수](../atl/reference-counting.md) \-기술 기준이 결정 개체 \(또는 엄격 하 게, 인터페이스\) 더 이상이 사용 되 고 따라서 자체 제거 됩니다.  
  
-   [QueryInterface](../atl/queryinterface.md) \-개체는 지정 된 인터페이스에 대 한 쿼리를 사용 하는 방법.  
  
-   [마샬링](../atl/marshaling.md) \-개체를 통해 스레드, 프로세스 및 네트워크 경계에 위치 독립성을 사용할 수 있도록 하는 메커니즘입니다.  
  
-   [집계](../atl/aggregation.md) \-에서 하나의 개체 수 확인 하는 방법을 사용 중입니다.  
  
## 참고 항목  
 [Introduction to COM and ATL](../atl/introduction-to-com-and-atl.md)   
 [The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)