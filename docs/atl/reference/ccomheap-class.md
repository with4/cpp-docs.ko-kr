---
title: "CComHeap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComHeap"
  - "ATL.CComHeap"
  - "ATL::CComHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComHeap class"
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CComHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) COM 메모리 할당 함수를 사용 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CComHeap : public IAtlMemMgr  
  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComHeap::Allocate](../Topic/CComHeap::Allocate.md)|메모리 블록을 할당 하는 데이 메서드를 호출 합니다.|  
|[CComHeap::Free](../Topic/CComHeap::Free.md)|이 메모리 관리자에 의해 할당 된 메모리 블록을 확보 하려면이 메서드를 호출 합니다.|  
|[CComHeap::GetSize](../Topic/CComHeap::GetSize.md)|이 메모리 관리자가 할당 한 메모리 블록의 할당 된 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CComHeap::Reallocate](../Topic/CComHeap::Reallocate.md)|이 메모리 관리자에 의해 할당 된 메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CComHeap`메모리 할당 함수를 포함 하 여 COM 할당 함수를 사용 하 여 구현  [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727),  [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722),  [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226), 및  [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280).  할당할 수 있는 메모리의 최대 양을 같지  **INT\_MAX** \(2147483647\) 바이트입니다.  
  
## 예제  
 예제를 보려면  [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## 상속 계층 구조  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## 요구 사항  
 **헤더:** ATLComMem.h  
  
## 참고 항목  
 [DynamicConsumer 샘플](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap Class](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)