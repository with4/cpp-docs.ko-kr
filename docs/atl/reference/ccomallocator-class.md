---
title: "CComAllocator 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComAllocator
- ATL::CComAllocator
- CComAllocator
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: d395d347e81b24462a41de5ae3b9d8791d7f82fd
ms.lasthandoff: 02/24/2017

---
# <a name="ccomallocator-class"></a>CComAllocator 클래스
이 클래스는 COM 메모리 루틴을 사용 하 여 메모리를 관리 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComAllocator
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|메모리를 할당 하려면이 정적 메서드를 호출 합니다.|  
|[CComAllocator::Free](#free)|할당 된 메모리를이 정적 메서드를 호출 합니다.|  
|[CComAllocator::Reallocate](#reallocate)|메모리를 할당 하기 위하여이 정적 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 사용 하 여 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) COM 메모리 할당 루틴을 제공 하기. 해당 클래스 [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), CRT 루틴을 사용 하 여 동일한 메서드를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="a-nameallocatea--ccomallocatorallocate"></a><a name="allocate"></a>CComAllocator::Allocate  
 메모리를 할당하려면 이 정적 함수를 호출합니다.  
  
```
static void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 할당할 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 할당된 공간에 대한 void 포인터 또는 사용 가능한 메모리가 부족한 경우 NULL을 반환합니다.  
  
### <a name="remarks"></a>주의  
 메모리를 할당합니다. 참조 [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727) 대 한 자세한 내용은 합니다.  
  
##  <a name="a-namefreea--ccomallocatorfree"></a><a name="free"></a>CComAllocator::Free  
 할당 된 메모리를 정적이 함수를 호출 합니다.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 할당된 메모리에 대한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 할당된 된 메모리를 해제합니다. 참조 [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) 대 한 자세한 내용은 합니다.  
  
##  <a name="a-namereallocatea--ccomallocatorreallocate"></a><a name="reallocate"></a>CComAllocator::Reallocate  
 메모리를 다시 할당하려면 이 정적 함수를 호출합니다.  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 할당된 메모리에 대한 포인터입니다.  
  
 `nBytes`  
 다시 할당할 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리가 부족 한 경우 할당 된 공간 또는 NULL로는 void 포인터를 반환  
  
### <a name="remarks"></a>주의  
 할당된 메모리의 크기를 조정합니다. 참조 [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280) 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComHeapPtr 클래스](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator 클래스](../../atl/reference/ccrtallocator-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

