---
title: "ATL Collection and Enumerator Classes | Microsoft Docs"
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
  - "컬렉션 클래스, ATL"
  - "열거자, ATL 클래스"
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL Collection and Enumerator Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 컬렉션 및 열거자를 구현 하는 데 도움이 되는 다음 클래스를 제공 합니다.  
  
|클래스|설명|  
|---------|--------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|컬렉션 인터페이스 구현|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|열거자 인터페이스 구현에 \(호환 STL 컨테이너에 저장 된 데이터 가정\)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|열거자 인터페이스 구현 \(배열에 저장 된 데이터를 가정\)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|열거자 개체 구현 \(사용 `IEnumOnSTLImpl`\)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|열거자 개체 구현 \(사용 `CComEnumImpl`\)|  
|[\_Copy](../atl/atl-copy-policy-classes.md)|복사 정책 클래스|  
|[\_CopyInterface](../atl/atl-copy-policy-classes.md)|복사 정책 클래스|  
|[CAdapt](../atl/reference/cadapt-class.md)|어댑터 클래스 \(숨깁니다  **연산자 &** 허용 `CComPtr`, `CComQIPtr`, 및 `CComBSTR` STL 컨테이너에 저장\)|  
  
## 참고 항목  
 [컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)