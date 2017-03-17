---
title: "CComHeap 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 323ad1aed4bae706ecbf66de769e33873f20c149
ms.lasthandoff: 02/24/2017

---
# <a name="ccomheap-class"></a>CComHeap 클래스
이 클래스는 구현 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) COM 메모리 할당 함수를 사용 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComHeap::Allocate](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|  
|[CComHeap::Free](#free)|이 메모리 관리자가 할당 한 메모리 블록을 해제 하려면이 메서드를 호출 합니다.|  
|[CComHeap::GetSize](#getsize)|이 메모리 관리자가 할당 된 메모리 블록의 할당된 된 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CComHeap::Reallocate](#reallocate)|이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.|  
  
## <a name="remarks"></a>주의  
 `CComHeap`메모리 할당 함수를 포함 하 여 COM 할당 기능을 사용 하 여 구현 [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226), 및 [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)합니다. 할당 될 수 있는 메모리의 최대 용량은 같지 **INT_MAX** (2147483647) 바이트입니다.  
  
## <a name="example"></a>예제  
 예를 참조 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ATLComMem.h  
  
##  <a name="allocate"></a>CComHeap::Allocate  
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
 호출 [CComHeap::Free](#free) 또는 [CComHeap::Reallocate](#reallocate) 이 메서드에서 할당 된 메모리를 해제 합니다.  
  
 사용 하 여 구현 [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)합니다.  
  
##  <a name="free"></a>CComHeap::Free  
 이 메모리 관리자가 할당 한 메모리 블록을 해제 하려면이 메서드를 호출 합니다.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다. NULL은 유효한 값이 고는 아무 작업도 수행 합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 구현 [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)합니다.  
  
##  <a name="getsize"></a>CComHeap::GetSize  
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
 사용 하 여 구현 [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226)합니다.  
  
##  <a name="reallocate"></a>CComHeap::Reallocate  
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
 호출 [CComHeap::Free](#free) 이 메서드에서 할당 된 메모리를 해제 합니다.  
  
 사용 하 여 구현 [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DynamicConsumer 샘플](../../visual-cpp-samples.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CWin32Heap 클래스](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap 클래스](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap 클래스](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap 클래스](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)

