---
title: "CInterfaceList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CInterfaceList"
  - "ATL.CInterfaceList"
  - "CInterfaceList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterfaceList class"
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CInterfaceList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 COM 인터페이스 포인터 목록을 구성할 때 유용한 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   class I,  
   const IID* piid = & __uuidof( I )  
>   
class CInterfaceList : public CAtlList<  
   ATL::CComQIPtr< I, piid >,  
   CComQIPtrElementTraits< I, piid >  
>  
```  
  
#### 매개 변수  
 `I`  
 저장 되는 포인터 유형을 지정 하는 COM 인터페이스입니다.  
  
 `piid`  
 IID에 대 한 포인터 `I`.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CInterfaceList::CInterfaceList](../Topic/CInterfaceList::CInterfaceList.md)|인터페이스 목록에 대 한 생성자입니다.|  
  
## 설명  
 이 클래스에는 생성자 및 파생된 COM 인터페이스 포인터의 목록을 만드는 방법을 제공 합니다.  사용  [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 때 배열이 필요 합니다.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 상속 계층 구조  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CAtlList Class](../../atl/reference/catllist-class.md)   
 [CComQIPtr Class](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits Class](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)