---
title: "CComObject Class | Microsoft Docs"
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
  - "ATL.CComObject<Base>"
  - "ATL::CComObject"
  - "ATL::CComObject<Base>"
  - "ATL.CComObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObject class"
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  **IUnknown** 의 집합체입니다.  
  
## 구문  
  
```  
  
      template<  
   class Base   
>  
class CComObject :  
   public Base  
```  
  
#### 매개 변수  
 `Base`  
 파생 클래스에서  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지 원하는 다른 인터페이스 이름으로 원하는 대로.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComObject::CComObject](../Topic/CComObject::CComObject.md)|생성자입니다.|  
|[CComObject::~CComObject](../Topic/CComObject::~CComObject.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComObject::AddRef](../Topic/CComObject::AddRef.md)|개체의 참조 횟수를 증가 시킵니다.|  
|[CComObject::CreateInstance](../Topic/CComObject::CreateInstance.md)|\(정적\) 새 `CComObject` 개체입니다.|  
|[CComObject::QueryInterface](../Topic/CComObject::QueryInterface.md)|요청 된 인터페이스에 대 한 포인터를 검색합니다.|  
|[CComObject::Release](../Topic/CComObject::Release.md)|개체의 참조 횟수를 감소 시킵니다.|  
  
## 설명  
 `CComObject`구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 의 집합체입니다.  그러나 호출 `QueryInterface`, `AddRef`, 및  **릴리스** 에 위임 된 `CComObjectRootEx`.  
  
 사용에 대 한 자세한 내용은 `CComObject`, 문서를 참조 하십시오.  [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md).  
  
## 상속 계층 구조  
 `Base`  
  
 `CComObject`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)