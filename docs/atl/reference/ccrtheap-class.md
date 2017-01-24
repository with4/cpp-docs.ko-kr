---
title: "CCRTHeap Class | Microsoft Docs"
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
  - "ATL::CCRTHeap"
  - "ATL.CCRTHeap"
  - "CCRTHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTHeap class"
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCRTHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) CRT 힙 함수를 사용 합니다.  
  
## 구문  
  
```  
  
class CCRTHeap : public IAtlMemMgr  
  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CCRTHeap::Allocate](../Topic/CCRTHeap::Allocate.md)|메모리 블록을 할당 하는 데이 메서드를 호출 합니다.|  
|[CCRTHeap::Free](../Topic/CCRTHeap::Free.md)|이 메모리 관리자에 의해 할당 된 메모리 블록을 확보 하려면이 메서드를 호출 합니다.|  
|[CCRTHeap::GetSize](../Topic/CCRTHeap::GetSize.md)|이 메모리 관리자가 할당 한 메모리 블록의 할당 된 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CCRTHeap::Reallocate](../Topic/CCRTHeap::Reallocate.md)|이 메모리 관리자에 의해 할당 된 메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CCRTHeap`메모리 할당 함수는 CRT를 사용 하 여 함수를 포함 하 여 힙 구현  [malloc](../../c-runtime-library/reference/malloc.md),  [사용 가능한](../../c-runtime-library/reference/free.md),  [realloc](../../c-runtime-library/reference/realloc.md), 및  [\_msize](../../c-runtime-library/reference/msize.md).  
  
## 예제  
 예제를 보려면  [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## 상속 계층 구조  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## 요구 사항  
 **헤더:** atlmem.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)