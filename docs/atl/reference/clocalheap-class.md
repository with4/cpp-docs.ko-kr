---
title: "CLocalHeap Class | Microsoft Docs"
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
  - "ATL.CLocalHeap"
  - "ATL::CLocalHeap"
  - "CLocalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLocalHeap class"
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLocalHeap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 로컬 힙 함수를 사용 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CLocalHeap : public IAtlMemMgr  
  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CLocalHeap::Allocate](../Topic/CLocalHeap::Allocate.md)|메모리 블록을 할당 하는 데이 메서드를 호출 합니다.|  
|[CLocalHeap::Free](../Topic/CLocalHeap::Free.md)|이 메모리 관리자에 의해 할당 된 메모리 블록을 확보 하려면이 메서드를 호출 합니다.|  
|[CLocalHeap::GetSize](../Topic/CLocalHeap::GetSize.md)|이 메모리 관리자가 할당 한 메모리 블록의 할당 된 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CLocalHeap::Reallocate](../Topic/CLocalHeap::Reallocate.md)|이 메모리 관리자에 의해 할당 된 메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CLocalHeap`Win32 로컬 힙 함수를 사용 하 여 메모리 할당 함수를 구현 합니다.  
  
> [!NOTE]
>  로컬 힙 함수의 다른 메모리 관리 기능 보다 느립니다 및 많은 기능을 제공 하지 않습니다.  따라서 새 응용 프로그램을 사용 해야는  [힙 함수](http://msdn.microsoft.com/library/windows/desktop/aa366711).  여기에 사용할 수 있는  [는 CWin32Heap](../../atl/reference/cwin32heap-class.md) 클래스.  
  
## 예제  
 예제를 보려면  [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## 상속 계층 구조  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## 요구 사항  
 **헤더:** atlmem.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComHeap Class](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap Class](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap Class](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap Class](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr Class](../../atl/reference/iatlmemmgr-class.md)