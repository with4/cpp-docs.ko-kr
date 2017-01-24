---
title: "CHeapPtrBase Class | Microsoft Docs"
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
  - "ATL.CHeapPtrBase"
  - "ATL::CHeapPtrBase"
  - "CHeapPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrBase class"
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtrBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 여러 스마트 힙 포인터 클래스에 대 한 기초가 됩니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
class Allocator= CCRTAllocator   
> class CHeapPtrBase  
```  
  
#### 매개 변수  
 `T`  
 힙에 저장 될 개체의 형식입니다.  
  
 `Allocator`  
 사용 하는 메모리 할당 클래스입니다.  기본적으로 CRT 루틴이 할당 한 메모리를 확보 하려면 사용 됩니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHeapPtrBase::~CHeapPtrBase](../Topic/CHeapPtrBase::~CHeapPtrBase.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHeapPtrBase::AllocateBytes](../Topic/CHeapPtrBase::AllocateBytes.md)|메모리를 할당 하는 데이 메서드를 호출 합니다.|  
|[CHeapPtrBase::Attach](../Topic/CHeapPtrBase::Attach.md)|기존 포인터의 소유권을 가져오려면이 메서드를 호출 합니다.|  
|[CHeapPtrBase::Detach](../Topic/CHeapPtrBase::Detach.md)|소유권에 대 한 포인터를 해제 하려면이 메서드를 호출 합니다.|  
|[CHeapPtrBase::Free](../Topic/CHeapPtrBase::Free.md)|가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CHeapPtrBase`.|  
|[CHeapPtrBase::ReallocateBytes](../Topic/CHeapPtrBase::ReallocateBytes.md)|메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CHeapPtrBase::operator T\*](../Topic/CHeapPtrBase::operator%20T*.md)|캐스트 연산자입니다.|  
|[CHeapPtrBase::operator &](../Topic/CHeapPtrBase::operator%20&.md)|& 연산자.|  
|[CHeapPtrBase::operator \-\>](../Topic/CHeapPtrBase::operator%20-%3E.md)|포인터 멤버 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CHeapPtrBase::m\_pData](../Topic/CHeapPtrBase::m_pData.md)|포인터 데이터 멤버 변수입니다.|  
  
## 설명  
 이 클래스는 여러 스마트 힙 포인터 클래스에 대 한 기초가 됩니다.  예를 들어, 파생된 클래스  [CHeapPtr](../../atl/reference/cheapptr-class.md) 및  [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), 자신의 생성자와 연산자를 추가 합니다.  이러한 클래스에 구현 예제를 참조 하십시오.  
  
## 요구 사항  
 **헤더:** atlcore.h  
  
## 참고 항목  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)