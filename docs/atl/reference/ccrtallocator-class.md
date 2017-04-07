---
title: "CCRTAllocator 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
ms.openlocfilehash: 5154a095409705e96dee6f52c67d7c23b0e6691f
ms.lasthandoff: 02/24/2017

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
|[CCRTAllocator::Allocate](#allocate)|(정적) 메모리를 할당 하려면이 메서드를 호출 합니다.|  
|[CCRTAllocator::Free](#free)|(정적) 메모리를 해제 하려면이 메서드를 호출 합니다.|  
|[CCRTAllocator::Reallocate](#reallocate)|(정적) 메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 사용 하 여 [CHeapPtr](../../atl/reference/cheapptr-class.md) CRT 메모리 할당 루틴을 제공 하기. 해당 클래스 [CComAllocator](../../atl/reference/ccomallocator-class.md), COM 루틴을 사용 하 여 동일한 메서드를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="allocate"></a>CCRTAllocator::Allocate  
 메모리를 할당하려면 이 정적 함수를 호출합니다.  
  
```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 할당할 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 할당된 공간에 대한 void 포인터 또는 사용 가능한 메모리가 부족한 경우 NULL을 반환합니다.  
  
### <a name="remarks"></a>주의  
 메모리를 할당합니다. 참조 [malloc](../../c-runtime-library/reference/malloc.md) 대 한 자세한 내용은 합니다.  
  
##  <a name="free"></a>CCRTAllocator::Free  
 메모리를 정적이 함수를 호출 합니다.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 할당된 메모리에 대한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 할당된 된 메모리를 해제합니다. 참조 [무료](../../c-runtime-library/reference/free.md) 대 한 자세한 내용은 합니다.  
  
##  <a name="reallocate"></a>CCRTAllocator::Reallocate  
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
  
### <a name="remarks"></a>주의  
 할당된 메모리의 크기를 조정합니다. 참조 [realloc](../../c-runtime-library/reference/realloc.md) 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)   
 [CComAllocator 클래스](../../atl/reference/ccomallocator-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

