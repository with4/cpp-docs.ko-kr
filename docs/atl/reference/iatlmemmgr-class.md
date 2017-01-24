---
title: "IAtlMemMgr Class | Microsoft Docs"
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
  - "IAtlMemMgr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlMemMgr class"
  - "메모리, 관리"
  - "메모리, memory manager"
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAtlMemMgr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 인터페이스를 메모리 관리자를 나타냅니다.  
  
## 구문  
  
```  
  
__interface __declspec( uuid( "654F7EF5-CFDF-4df9-A450-6C6A13C622C0" )) IAtlMemMgr  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[할당](../Topic/IAtlMemMgr::Allocate.md)|메모리 블록을 할당 하는 데이 메서드를 호출 합니다.|  
|[자유형](../Topic/IAtlMemMgr::Free.md)|메모리 블록을 확보 하려면이 메서드를 호출 합니다.|  
|[GetSize](../Topic/IAtlMemMgr::GetSize.md)|할당 된 메모리 블록의 크기를 검색 하려면이 메서드를 호출 합니다.|  
|[다시 할당](../Topic/IAtlMemMgr::Reallocate.md)|메모리 블록을 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 이 인터페이스에 의해 구현 된  [CComHeap](../../atl/reference/ccomheap-class.md),  [CCRTHeap](../../atl/reference/ccrtheap-class.md),  [CLocalHeap](../../atl/reference/clocalheap-class.md),  [CGlobalHeap](../../atl/reference/cglobalheap-class.md), 또는  [는 CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
> [!NOTE]
>  로컬 및 전역 힙 함수는 다른 메모리 관리 기능 보다 느립니다 및 많은 기능을 제공 하지 않습니다.  따라서 새 응용 프로그램을 사용 해야는  [힙 함수](http://msdn.microsoft.com/library/windows/desktop/aa366711).  여기에 사용할 수 있는  [는 CWin32Heap](../../atl/reference/cwin32heap-class.md) 클래스.  
  
## 예제  
 [!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/CPP/iatlmemmgr-class_1.cpp)]  
  
## 요구 사항  
 **헤더:** atlmem.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)