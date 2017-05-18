---
title: "CGlobalHeap 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f8b4276202a507e2afeb05d10a37fa16565870e8
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cglobalheap-class"></a>CGlobalHeap 클래스
이 클래스는 구현 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 글로벌 힙 함수를 사용 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CGlobalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CGlobalHeap::Allocate](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|  
|[CGlobalHeap::Free](#free)|이 메모리 관리자가 할당 한 메모리 블록을 해제 하려면이 메서드를 호출 합니다.|  
|[CGlobalHeap::GetSize](#getsize)|이 메모리 관리자가 할당 된 메모리 블록의 할당된 된 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CGlobalHeap::Reallocate](#reallocate)|이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.|  
  
## <a name="remarks"></a>주의  
 `CGlobalHeap`Win32 글로벌 힙 함수를 사용 하 여 메모리 할당 함수를 구현 합니다.  
  
> [!NOTE]
>  전역 힙 함수는 다른 메모리 관리 함수 보다 느립니다 및 많은 기능을 제공 하지 않습니다. 따라서 새 응용 프로그램을 사용 해야는 [함수 힙](http://msdn.microsoft.com/library/windows/desktop/aa366711)합니다. 사용할 수는 [CWin32Heap](../../atl/reference/cwin32heap-class.md) 클래스입니다. 전역 함수 DDE 및 클립보드 함수에서 계속 사용 됩니다.  
  
## <a name="example"></a>예제  
 예를 참조 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlmem.h  
  
##  <a name="allocate"></a>CGlobalHeap::Allocate  
 메모리 블록을 할당하려면 이 메서드를 호출합니다.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 새 메모리 블록의 요청된 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.  
  
### <a name="remarks"></a>주의  
 호출 [CGlobalHeap::Free](#free) 또는 [CGlobalHeap::Reallocate](#reallocate) 이 메서드에서 할당 된 메모리를 해제 합니다.  
  
 사용 하 여 구현 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) 플래그 매개 변수 **GMEM_FIXED**합니다.  
  
##  <a name="free"></a>CGlobalHeap::Free  
 이 메모리 관리자가 할당 한 메모리 블록을 해제 하려면이 메서드를 호출 합니다.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다. NULL은 유효한 값이 고는 아무 작업도 수행 합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 구현 [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)합니다.  
  
##  <a name="getsize"></a>CGlobalHeap::GetSize  
 이 메모리 관리자가 할당 된 메모리 블록의 할당된 된 크기를 가져오려면이 메서드를 호출 합니다.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 할당 된 메모리 블록의 크기 (바이트)를 반환합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 구현 [GlobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593)합니다.  
  
##  <a name="reallocate"></a>CGlobalHeap::Reallocate  
 이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.  
  
 `nBytes`  
 새 메모리 블록의 요청된 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.  
  
### <a name="remarks"></a>주의  
 호출 [CGlobalHeap::Free](#free) 이 메서드에서 할당 된 메모리를 해제 합니다.  
  
 사용 하 여 구현 [GlobalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366590)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CComHeap 클래스](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap 클래스](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap 클래스](../../atl/reference/clocalheap-class.md)   
 [CCRTHeap 클래스](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)

