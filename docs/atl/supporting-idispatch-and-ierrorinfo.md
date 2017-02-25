---
title: "IDispatch 및 IErrorInfo 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorInfo"
  - "IDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL에서의 IDispatch 클래스 지원"
  - "IDispatchImpl 클래스"
  - "ATL에서의 IErrorInfo 클래스 지원"
  - "ISupportErrorInfoImpl 메서드"
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# IDispatch 및 IErrorInfo 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스를 사용할 수 있습니다  [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 의 기본 구현을 제공 하는 `IDispatch Interface` 개체에서 이중 인터페이스 부분.  
  
 개체를 사용 하는 경우는 `IErrorInfo` 보고 오류 다시 클라이언트에 다음 개체를 지원 해야 하는 인터페이스는 `ISupportErrorInfo Interface` 인터페이스.  템플릿 클래스  [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 오류 개체를 생성 하는 단일 인터페이스를만 있을 경우이 구현할 수 있습니다.  
  
## 참고 항목  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)