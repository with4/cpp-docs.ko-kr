---
title: "CAutoVectorPtr Class | Microsoft Docs"
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
  - "ATL::CAutoVectorPtr"
  - "ATL.CAutoVectorPtr"
  - "ATL.CAutoVectorPtr<T>"
  - "CAutoVectorPtr"
  - "ATL::CAutoVectorPtr<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoVectorPtr class"
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoVectorPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 새 벡터를 사용 하 여 스마트 포인터가 개체를 나타내는 및 연산자 삭제.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
typename T  
> class CAutoVectorPtr  
```  
  
#### 매개 변수  
 `T`  
 포인터 형식입니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAutoVectorPtr::CAutoVectorPtr](../Topic/CAutoVectorPtr::CAutoVectorPtr.md)|생성자입니다.|  
|[CAutoVectorPtr::~CAutoVectorPtr](../Topic/CAutoVectorPtr::~CAutoVectorPtr.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAutoVectorPtr::Allocate](../Topic/CAutoVectorPtr::Allocate.md)|이 메서드는 배열을 가리키는 개체에 필요한 메모리를 할당할 수 호출 `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](../Topic/CAutoVectorPtr::Attach.md)|기존 포인터의 소유권을 가져오려면이 메서드를 호출 합니다.|  
|[CAutoVectorPtr::Detach](../Topic/CAutoVectorPtr::Detach.md)|소유권에 대 한 포인터를 해제 하려면이 메서드를 호출 합니다.|  
|[CAutoVectorPtr::Free](../Topic/CAutoVectorPtr::Free.md)|가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoVectorPtr`.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAutoVectorPtr::operator T \*](../Topic/CAutoVectorPtr::operator%20T%20*.md)|캐스트 연산자입니다.|  
|[CAutoVectorPtr::operator \=](../Topic/CAutoVectorPtr::operator%20=.md)|할당 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAutoVectorPtr::m\_p](../Topic/CAutoVectorPtr::m_p.md)|포인터 데이터 멤버 변수입니다.|  
  
## 설명  
 이 클래스 만들기 및 관리 범위를 벗어난 작아지면 리소스를 자동으로 해제 하 여 메모리 누수를 방지 하는 데 도움이 되는 스마트 포인터에 대 한 메서드를 제공 합니다.  `CAutoVectorPtr`유사 합니다 `CAutoPtr`, 유일한 차이점은 되 고 `CAutoVectorPtr` 를 사용 하 여  [벡터 new](../Topic/operator%20new\(%3Cnew%3E\).md) 및  [벡터 delete](../Topic/operator%20delete\(%3Cnew%3E\).md) 할당 및 C\+\+ 대신 메모리를 해제 하  **새** 및  **삭제** 연산자.  참조  [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) 경우 컬렉션 클래스의 `CAutoVectorPtr` 필요 합니다.  
  
 참조  [CAutoPtr](../../atl/reference/cautoptr-class.md) 에 대 한 스마트 포인터 클래스를 사용 하는 예제입니다.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [CAutoPtr Class](../../atl/reference/cautoptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)