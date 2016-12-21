---
title: "CHeapPtr Class | Microsoft Docs"
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
  - "ATL::CHeapPtr"
  - "CHeapPtr"
  - "ATL.CHeapPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtr class"
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙 포인터를 관리 하는 스마트 포인터 클래스입니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
typename T,  
class Allocator= CCRTAllocator  
> class CHeapPtr :  
public CHeapPtrBase< T, Allocator>  
```  
  
#### 매개 변수  
 `T`  
 힙에 저장 될 개체의 형식입니다.  
  
 `Allocator`  
 사용 하는 메모리 할당 클래스입니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHeapPtr::CHeapPtr](../Topic/CHeapPtr::CHeapPtr.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHeapPtr::Allocate](../Topic/CHeapPtr::Allocate.md)|저장할 개체 힙에 메모리를 할당 하려면이 메서드를 호출 합니다.|  
|[CHeapPtr::Reallocate](../Topic/CHeapPtr::Reallocate.md)|힙에 메모리를 할당 하려면이 메서드를 호출 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CHeapPtr::operator \=](../Topic/CHeapPtr::operator%20=.md)|할당 연산자입니다.|  
  
## 설명  
 `CHeapPtr`파생 된  [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) 기본적으로 CRT 루틴이 사용 \(에서  [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)\) 할당 하 고 메모리를 해제 합니다.  클래스  [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) 힙 포인터 목록을 만드는 데 사용할 수 있습니다.  참고  [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), COM 메모리 할당 루틴을 사용 합니다.  
  
## 상속 계층 구조  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## 요구 사항  
 **헤더:** atlcore.h  
  
## 참고 항목  
 [CHeapPtrBase Class](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator Class](../../atl/reference/ccrtallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)