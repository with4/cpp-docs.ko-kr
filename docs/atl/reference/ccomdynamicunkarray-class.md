---
title: "CComDynamicUnkArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComDynamicUnkArray"
  - "CComDynamicUnkArray"
  - "ATL::CComDynamicUnkArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComDynamicUnkArray class"
  - "연결 지점[C++], 관리"
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CComDynamicUnkArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 배열을 저장  **IUnknown** 포인터.  
  
## 구문  
  
```  
class CComDynamicUnkArray  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](../Topic/CComDynamicUnkArray::CComDynamicUnkArray.md)|생성자입니다.  컬렉션 값을 초기화  **NULL** 컬렉션 크기를 0으로 하 고 있습니다.|  
|[CComDynamicUnkArray::~CComDynamicUnkArray](../Topic/CComDynamicUnkArray::~CComDynamicUnkArray.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComDynamicUnkArray::Add](../Topic/CComDynamicUnkArray::Add.md)|추가 하려면이 메서드를 호출 하는 `IUnknown` 배열에 대 한 포인터입니다.|  
|[CComDynamicUnkArray::begin](../Topic/CComDynamicUnkArray::begin.md)|처음에는 포인터를 반환 합니다. `IUnknown` 컬렉션에 대 한 포인터.|  
|[CComDynamicUnkArray::clear](../Topic/CComDynamicUnkArray::clear.md)|배열을 비웁니다.|  
|[CComDynamicUnkArray::end](../Topic/CComDynamicUnkArray::end.md)|지난 마지막 하나에 포인터를 반환 합니다.  **IUnknown** 컬렉션에 대 한 포인터입니다.|  
|[CComDynamicUnkArray::GetAt](../Topic/CComDynamicUnkArray::GetAt.md)|지정된 인덱스에 있는 요소를 검색합니다.|  
|[CComDynamicUnkArray::GetCookie](../Topic/CComDynamicUnkArray::GetCookie.md)|관련 된 쿠키를 가져오려면이 메서드를 호출 하는 지정 된  **IUnknown** 포인터.|  
|[CComDynamicUnkArray::GetSize](../Topic/CComDynamicUnkArray::GetSize.md)|배열의 길이를 반환합니다.|  
|[CComDynamicUnkArray::GetUnknown](../Topic/CComDynamicUnkArray::GetUnknown.md)|가져오려면이 메서드를 호출 하는  **IUnknown** 지정 된 쿠키와 관련 된 포인터.|  
|[CComDynamicUnkArray::Remove](../Topic/CComDynamicUnkArray::Remove.md)|제거 하려면이 메서드를 호출 하는  **IUnknown** 배열의 포인터.|  
  
## 설명  
 **CComDynamicUnkArray** 동적으로 할당 된 배열을 보유  **IUnknown** 포인터를 각 인터페이스에서 연결을 가리킵니다.  **CComDynamicUnkArray** 매개 변수로 사용할 수 있는  [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스입니다.  
  
 **CComDynamicUnkArray** 메서드  [시작](../Topic/CComDynamicUnkArray::begin.md) 및  [최종](../Topic/CComDynamicUnkArray::end.md) \(예를 들어, 이벤트가 발생 하는 경우\) 모든 연결점을 순환 검색 하려면 사용할 수 있습니다.  
  
 참조 [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md) 지점 프록시 연결 만들기 자동화에 대 한 자세한.  
  
> [!NOTE]
>  **참고** 클래스는  **CComDynamicUnkArray** 사용 되는  **클래스 추가** 연결점이 있는 컨트롤을 만들 때 마법사.  연결 지점을 수동으로 지정 하려는 경우 참조 변경  **CComDynamicUnkArray** 에 `CComUnkArray<` *n* `>`여기서  *n* 필요한 연결점입니다.  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComUnkArray Class](../../atl/reference/ccomunkarray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)