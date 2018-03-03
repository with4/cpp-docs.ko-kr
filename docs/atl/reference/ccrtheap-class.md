---
title: "CCRTHeap 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9864ce3522cf33927a3f6d3572e9d2e12187f5d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccrtheap-class"></a>CCRTHeap 클래스
이 클래스는 구현 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) CRT 힙 함수를 사용 하 여 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CCRTHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Ccrtheap:: Allocate](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|  
|[Ccrtheap::](#free)|이 메모리 관리자에 의해 할당 된 메모리 블록을 해제 하려면이 메서드를 호출 합니다.|  
|[CCRTHeap::GetSize](#getsize)|이 메모리 관리자에 의해 할당 된 메모리 블록의 할당 된 크기를 가져오려면이 메서드를 호출 합니다.|  
|[Ccrtheap:: Reallocate](#reallocate)|이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.|  
  
## <a name="remarks"></a>설명  
 `CCRTHeap`메모리 할당 함수 CRT를 사용 하 여 힙 함수를 포함 하 여 구현 [malloc](../../c-runtime-library/reference/malloc.md), [무료](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md), 및 [_msize](../../c-runtime-library/reference/msize.md)합니다.  
  
## <a name="example"></a>예  
 예를 참조 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlmem.h  
  
##  <a name="allocate"></a>Ccrtheap:: Allocate  
 메모리 블록을 할당하려면 이 메서드를 호출합니다.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 새 메모리 블록의 요청된 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.  
  
### <a name="remarks"></a>설명  
 호출 [ccrtheap::](#free) 또는 [ccrtheap:: Reallocate](#reallocate) 이 메서드에 의해 할당 된 메모리를 해제 합니다.  
  
 사용 하 여 구현 [malloc](../../c-runtime-library/reference/malloc.md)합니다.  
  
##  <a name="free"></a>Ccrtheap::  
 이 메모리 관리자에 의해 할당 된 메모리 블록을 해제 하려면이 메서드를 호출 합니다.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다. NULL은 올바른 값이 고 아무 작업도 수행 합니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 구현 [무료](../../c-runtime-library/reference/free.md)합니다.  
  
##  <a name="getsize"></a>CCRTHeap::GetSize  
 이 메모리 관리자에 의해 할당 된 메모리 블록의 할당 된 크기를 가져오려면이 메서드를 호출 합니다.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 할당 된 메모리 블록의 크기를 바이트 단위로 반환 합니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 구현 [_msize](../../c-runtime-library/reference/msize.md)합니다.  
  
##  <a name="reallocate"></a>Ccrtheap:: Reallocate  
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
  
### <a name="remarks"></a>설명  
 호출 [ccrtheap::](#free) 이 메서드에 의해 할당 된 메모리를 해제 합니다. 사용 하 여 구현 [realloc](../../c-runtime-library/reference/realloc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CComHeap 클래스](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap 클래스](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap 클래스](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap 클래스](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)
