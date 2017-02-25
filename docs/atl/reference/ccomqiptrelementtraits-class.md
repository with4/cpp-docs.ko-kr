---
title: "CComQIPtrElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComQIPtrElementTraits"
  - "CComQIPtrElementTraits"
  - "ATL::CComQIPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComQIPtrElementTraits class"
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComQIPtrElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 COM 인터페이스 포인터의 컬렉션을 만들 때 메서드, 정적 함수 및 형식 정의 유용 하 게 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   typename I,  
   const IID* piid = & __uuidof( I )   
>   
class CComQIPtrElementTraits : public CDefaultElementTraits<  
   ATL::CComQIPtr< I, piid >  
>  
```  
  
#### 매개 변수  
 `I`  
 저장 되는 포인터 유형을 지정 하는 COM 인터페이스입니다.  
  
 `piid`  
 IID에 대 한 포인터 `I`.  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CComQIPtrElementTraits::INARGTYPE](../Topic/CComQIPtrElementTraits::INARGTYPE.md)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하는 데이터 형식입니다.|  
  
## 설명  
 이 클래스 메서드를 파생 하 고 유용한 형식 정의의 컬렉션 클래스를 만들 때 제공  [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM 인터페이스 포인터 개체입니다.  이 클래스에서 모두 활용 되는  [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 및  [CInterfaceList](../../atl/reference/cinterfacelist-class.md) 클래스.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 상속 계층 구조  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)