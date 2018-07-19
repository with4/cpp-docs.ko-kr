---
title: CHeapPtr 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06c66f274ab2302689afdeda195c735d7a6e5069
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884495"
---
# <a name="cheapptr-class"></a>CHeapPtr 클래스
힙 포인터를 관리 하는 것에 대 한 스마트 포인터 클래스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T, class Allocator=CCRTAllocator>  
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 힙에 저장 될 개체 형식입니다.  
  
 *할당자*  
 사용 하는 메모리 할당 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](#cheapptr)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHeapPtr::Allocate](#allocate)|개체를 저장 하는 힙에 메모리를 할당 하려면이 메서드를 호출 합니다.|  
|[CHeapPtr::Reallocate](#reallocate)|힙에서 메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CHeapPtr::operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>설명  
 `CHeapPtr` 파생 됩니다 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) 기본적으로 CRT 루틴을 사용 하 고 (에 [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) 할당 및 메모리를 해제 합니다. 클래스 [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) 힙 포인터 목록을 만드는 데 사용할 수 있습니다. 참고 항목 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), COM 메모리 할당 루틴을 사용 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="allocate"></a>  CHeapPtr::Allocate  
 개체를 저장 하는 힙에 메모리를 할당 하려면이 메서드를 호출 합니다.  
  
```
bool Allocate(size_t nElements = 1) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *nElements*  
 할당할 메모리 양을 계산 하는 데 사용 되는 요소의 수입니다. 기본값은 1입니다.  
  
### <a name="return-value"></a>반환 값  
 True를 반환 했습니다. 메모리가 할당 실패 하면 false를 합니다.  
  
### <a name="remarks"></a>설명  
 할당자 루틴은 저장 하는 힙에 충분 한 메모리를 예약 하는 데 *nElement* 생성자에서 정의 된 형식의 개체입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]  
  
##  <a name="cheapptr"></a>  CHeapPtr::CHeapPtr  
 생성자입니다.  
  
```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *p*  
 기존 힙 포인터를 또는 `CHeapPtr`합니다.  
  
### <a name="remarks"></a>설명  
 기존 포인터를 사용 하 여 힙 포인터를 만들 수 있습니다 또는 `CHeapPtr` 개체입니다. 그렇다면 새 `CHeapPtr` 새 포인터 및 리소스 관리에 대 한 책임을 지지 하는 개체입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]  
  
##  <a name="operator_eq"></a>  CHeapPtr::operator =  
 대입 연산자입니다.  
  
```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *p*  
 기존 `CHeapPtr` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 참조를 반환 합니다 `CHeapPtr`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]  
  
##  <a name="reallocate"></a>  CHeapPtr::Reallocate  
 힙에서 메모리를 다시 할당 하려면이 메서드를 호출 합니다.  
  
```
bool Reallocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *nElements*  
 할당할 메모리 양을 계산 하는 데 사용 하는 요소의 새 수입니다.  
  
### <a name="return-value"></a>반환 값  
 True를 반환 했습니다. 메모리가 할당 실패 하면 false를 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CHeapPtrBase 클래스](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator 클래스](../../atl/reference/ccrtallocator-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
