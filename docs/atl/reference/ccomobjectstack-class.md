---
title: "CComObjectStack Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComObjectStack"
  - "ATL.CComObjectStack"
  - "ATL::CComObjectStack<Base>"
  - "ATL.CComObjectStack<Base>"
  - "CComObjectStack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectStack class"
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComObjectStack Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 임시 COM 개체를 만들고의 골격 구현을 통해 제공  **IUnknown**.  
  
## 구문  
  
```  
  
      template<  
   class Base   
>  
class CComObjectStack :  
   public Base  
```  
  
#### 매개 변수  
 `Base`  
 파생 클래스에서  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지 원하는 다른 인터페이스 이름으로 원하는 대로.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComObjectStack::CComObjectStack](../Topic/CComObjectStack::CComObjectStack.md)|생성자입니다.|  
|[CComObjectStack::~CComObjectStack](../Topic/CComObjectStack::~CComObjectStack.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComObjectStack::AddRef](../Topic/CComObjectStack::AddRef.md)|0을 반환 합니다.  디버그 모드에서 호출 `_ASSERTE`.|  
|[CComObjectStack::QueryInterface](../Topic/CComObjectStack::QueryInterface.md)|반환  **인터페이스**.  디버그 모드에서 호출 `_ASSERTE`.|  
|[CComObjectStack::Release](../Topic/CComObjectStack::Release.md)|0을 반환 합니다.  디버그 모드에서 호출 `_ASSERTE`.  ~|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CComObjectStack::m\_hResFinalConstruct](../Topic/CComObjectStack::m_hResFinalConstruct.md)|포함의  **HRESULT** 생성 하는 동안 반환 된 `CComObjectStack` 개체.|  
  
## 설명  
 `CComObjectStack`임시 COM 개체를 만들고 개체는 골격 구현을 제공 하는  **IUnknown**.  일반적으로 개체 \(스택으로 푸시됩니다,\) 함수 내에서 지역 변수로 사용 됩니다.  함수가 끝나면 개체가 소멸 되므로 참조 카운팅 효율을 수행 되지 않습니다.  
  
 다음은 함수 안에서 사용 하는 COM 개체를 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/CPP/ccomobjectstack-class_1.cpp)]  
  
 임시 개체 `Tempobj` 스택으로 푸시됩니다 및 함수가 완료 되 면 자동으로 사라집니다.  
  
## 상속 계층 구조  
 `Base`  
  
 `CComObjectStack`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal Class](../../atl/reference/ccomobjectglobal-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)