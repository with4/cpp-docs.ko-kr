---
title: "IAtlStringMgr Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAtlStringMgr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr class"
  - "메모리, 관리"
  - "shared classes, IAtlStringMgr"
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: 16
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAtlStringMgr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 인터페이스를 나타내는 한 `CStringT` 메모리 관리자.  
  
## 구문  
  
```  
  
__interface IAtlStringMgr  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[할당](../Topic/IAtlStringMgr::Allocate.md)|새 문자열 데이터 구조를 할당 하는 데이 메서드를 호출 합니다.|  
|[Clone](../Topic/IAtlStringMgr::Clone.md)|다른 인스턴스를 사용 하는 새 문자열 관리자에 포인터를 반환 하도록이 메서드를 호출 합니다. `CSimpleStringT`.|  
|[자유형](../Topic/IAtlStringMgr::Free.md)|문자열 데이터 구조를 해제 하려면이 메서드를 호출 합니다.|  
|[GetNilString](../Topic/IAtlStringMgr::GetNilString.md)|에 대 한 포인터를 반환의 `CStringData` 빈 string 개체에서 사용 하는 개체입니다.|  
|[다시 할당](../Topic/IAtlStringMgr::Reallocate.md)|문자열 데이터 구조를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 이 인터페이스는 독립적인 MFC string 클래스에 의해 사용 되는 메모리 관리. 같은  [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md),  [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), 및  [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 이 클래스 사용 하면 사용자 정의 메모리 관리자에 대 한 사용자 지정 문자열 클래스 구현  자세한 내용은  [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## 요구 사항  
 **헤더:** atlsimpstr.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)