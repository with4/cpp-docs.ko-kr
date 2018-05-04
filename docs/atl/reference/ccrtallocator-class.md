---
title: CCRTAllocator 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f92ae3f4041b143a8cc4d58b1060c7d5b9a7bb4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ccrtallocator-class"></a>CCRTAllocator 클래스
이 클래스는 CRT 메모리 루틴을 사용 하 여 메모리를 관리 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Ccrtallocator:: Allocate](#allocate)|(정적) 메모리를 할당 하려면이 메서드를 호출 합니다.|  
|[Ccrtallocator:: Free](#free)|(정적) 메모리를 해제 하려면이 메서드를 호출 합니다.|  
|[Ccrtallocator:: Allocate](#reallocate)|(정적) 메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 사용 하 여 [CHeapPtr](../../atl/reference/cheapptr-class.md) CRT 메모리 할당 루틴을 제공 하기. 테이블에 해당 클래스 [CComAllocator](../../atl/reference/ccomallocator-class.md), COM 루틴을 사용 하 여 동일한 메서드를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="allocate"></a>  Ccrtallocator:: Allocate  
 메모리를 할당하려면 이 정적 함수를 호출합니다.  
  
```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 할당할 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 할당된 공간에 대한 void 포인터 또는 사용 가능한 메모리가 부족한 경우 NULL을 반환합니다.  
  
### <a name="remarks"></a>설명  
 메모리를 할당합니다. 참조 [malloc](../../c-runtime-library/reference/malloc.md) 내용을 확인 합니다.  
  
##  <a name="free"></a>  Ccrtallocator:: Free  
 메모리를 해제 하려면이 정적 함수를 호출 합니다.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 할당된 메모리에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 할당된 된 메모리를 해제합니다. 참조 [무료](../../c-runtime-library/reference/free.md) 내용을 확인 합니다.  
  
##  <a name="reallocate"></a>  Ccrtallocator:: Allocate  
 메모리를 다시 할당하려면 이 정적 함수를 호출합니다.  
  
```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 할당된 메모리에 대한 포인터입니다.  
  
 `nBytes`  
 다시 할당할 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 할당된 공간에 대한 void 포인터 또는 메모리가 부족한 경우 NULL을 반환합니다.  
  
### <a name="remarks"></a>설명  
 할당된 메모리의 크기를 조정합니다. 참조 [realloc](../../c-runtime-library/reference/realloc.md) 내용을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)   
 [CComAllocator 클래스](../../atl/reference/ccomallocator-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
