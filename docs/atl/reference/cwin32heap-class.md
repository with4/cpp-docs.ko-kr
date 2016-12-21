---
title: "CWin32Heap Class | Microsoft Docs"
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
  - "ATL::CWin32Heap"
  - "ATL.CWin32Heap"
  - "CWin32Heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWin32Heap class"
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWin32Heap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 힙 할당 함수를 사용 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CWin32Heap : public IAtlMemMgr  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md)|생성자입니다.|  
|[CWin32Heap::~CWin32Heap](../Topic/CWin32Heap::~CWin32Heap.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWin32Heap::Allocate](../Topic/CWin32Heap::Allocate.md)|힙 개체에서 메모리 블록을 할당 합니다.|  
|[CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md)|하는 기존 힙 힙 개체를 연결합니다.|  
|[CWin32Heap::Detach](../Topic/CWin32Heap::Detach.md)|기존 힙에서 힙에 개체를 분리합니다.|  
|[CWin32Heap::Free](../Topic/CWin32Heap::Free.md)|이전에 힙에서 할당 된 메모리를 해제 합니다.|  
|[CWin32Heap::GetSize](../Topic/CWin32Heap::GetSize.md)|힙 개체에서 할당 한 메모리 블록의 크기를 반환 합니다.|  
|[CWin32Heap::Reallocate](../Topic/CWin32Heap::Reallocate.md)|메모리 블록에서 힙 개체를 다시 할당합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CWin32Heap::m\_bOwnHeap](../Topic/CWin32Heap::m_bOwnHeap.md)|힙 핸들의 현재 소유권을 확인 하는 데 사용 되는 플래그입니다.|  
|[CWin32Heap::m\_hHeap](../Topic/CWin32Heap::m_hHeap.md)|힙 개체를 처리 합니다.|  
  
## 설명  
 `CWin32Heap`메모리 할당 메서드를 포함 하 여 Win32 힙 할당 함수를 사용 하 여 구현  [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597) 및  [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701).  힙 다른 클래스와 달리 `CWin32Heap` 메모리를 할당 하기 전에 제공 하는 잘못 된 힙 핸들 필요: 기본 프로세스 힙에서 사용 하는 다른 클래스.  생성자 또는 핸들을 지정할 수 있는  [CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md) 메서드.  참조는  [CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md) 방법에 대 한 자세한 내용은.  
  
## 예제  
 예제를 보려면  [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## 상속 계층 구조  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## 요구 사항  
 **헤더:** atlmem.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)