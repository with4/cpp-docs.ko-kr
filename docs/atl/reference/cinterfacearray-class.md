---
title: "CInterfaceArray Class | Microsoft Docs"
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
  - "ATL.CInterfaceArray"
  - "CInterfaceArray"
  - "ATL::CInterfaceArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterfaceArray class"
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInterfaceArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 COM 인터페이스 포인터 배열을 구성할 때 유용한 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   class I,  
   const IID* piid = & __uuidof( I )  
>  
class CInterfaceArray : public CAtlArray<  
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
|[CInterfaceArray::CInterfaceArray](../Topic/CInterfaceArray::CInterfaceArray.md)|인터페이스의 배열에 대 한 생성자입니다.|  
  
## 설명  
 이 클래스 생성자 및 COM 인터페이스 포인터의 배열을 만드는 파생된 메서드를 제공 합니다.  사용  [CInterfaceList](../../atl/reference/cinterfacelist-class.md) 때 목록이 필요 합니다.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 상속 계층 구조  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CAtlArray Class](../../atl/reference/catlarray-class.md)   
 [CComQIPtr Class](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits Class](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)