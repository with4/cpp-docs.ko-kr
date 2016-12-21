---
title: "CComUnkArray Class | Microsoft Docs"
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
  - "ATL.CComUnkArray"
  - "ATL.CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray"
  - "CComUnkArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComUnkArray class"
  - "연결 지점[C++], 관리"
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComUnkArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 저장  **IUnknown** 포인터를 매개 변수로 사용 하도록 하 고 있는  [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스.  
  
## 구문  
  
```  
template<  
   unsigned int nMaxSize  
>  
class CComUnkArray  
```  
  
#### 매개 변수  
 *nMaxSize*  
 최대  **IUnknown** 포인터의 정적 배열을 보유 될 수 있습니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComUnkArray::CComUnkArray](../Topic/CComUnkArray::CComUnkArray.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComUnkArray::Add](../Topic/CComUnkArray::Add.md)|추가 하려면이 메서드를 호출 하는  **IUnknown** 배열에 대 한 포인터입니다.|  
|[CComUnkArray::begin](../Topic/CComUnkArray::begin.md)|처음에는 포인터를 반환 합니다.  **IUnknown** 컬렉션에 대 한 포인터.|  
|[CComUnkArray::end](../Topic/CComUnkArray::end.md)|지난 마지막 하나에 포인터를 반환 합니다.  **IUnknown** 컬렉션에 대 한 포인터입니다.|  
|[CComUnkArray::GetCookie](../Topic/CComUnkArray::GetCookie.md)|관련 된 쿠키를 가져오려면이 메서드를 호출 하는 지정 된  **IUnknown** 포인터.|  
|[CComUnkArray::GetUnknown](../Topic/CComUnkArray::GetUnknown.md)|가져오려면이 메서드를 호출 하는  **IUnknown** 지정 된 쿠키와 관련 된 포인터.|  
|[CComUnkArray::Remove](../Topic/CComUnkArray::Remove.md)|제거 하려면이 메서드를 호출 하는  **IUnknown** 배열의 포인터.|  
  
## 설명  
 **CComUnkArray** 고정 보유  **IUnknown** 포인터를 각 인터페이스에 대 한 연결을 가리킵니다.  **CComUnkArray** 매개 변수로 사용할 수 있는  [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스입니다.  **CComUnkArray \<1\>** 는 템플릿 특수화의  **CComUnkArray** 는 최적화 한 연결 지점에 대 한.  
  
 **CComUnkArray** 메서드  [시작](../Topic/CComUnkArray::begin.md) 및  [최종](../Topic/CComUnkArray::end.md) \(예를 들어, 이벤트가 발생 하는 경우\) 모든 연결점을 순환 검색 하려면 사용할 수 있습니다.  
  
 참조 [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md) 지점 프록시 연결 만들기 자동화에 대 한 자세한.  
  
> [!NOTE]
>  **참고** 클래스는  [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) 사용 되는  **클래스 추가** 연결점이 있는 컨트롤을 만들 때 마법사.  연결 지점을 수동으로 지정 하려는 경우 참조 변경  **CComDynamicUnkArray** 에 `CComUnkArray<` *n* `>`여기서  *n* 필요한 연결점입니다.  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComDynamicUnkArray Class](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)