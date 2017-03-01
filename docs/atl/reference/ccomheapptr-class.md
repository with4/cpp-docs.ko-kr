---
title: "CComHeapPtr 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComHeapPtr
- ATL.CComHeapPtr<T>
- ATL::CComHeapPtr<T>
- CComHeapPtr
- ATL.CComHeapPtr
dev_langs:
- C++
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 0e5196a98b8fd76b2e7e791fd2cd9549099a1cc9
ms.lasthandoff: 02/24/2017

---
# <a name="ccomheapptr-class"></a>CComHeapPtr 클래스
스마트 포인터는 힙에 대 한 포인터를 관리 하기 위한 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 힙에 저장 될 개체 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|생성자입니다.|  
  
## <a name="remarks"></a>주의  
 `CComHeapPtr`파생 `CHeapPtr`를 사용 하 여 [CComAllocator](../../atl/reference/ccomallocator-class.md) COM 루틴을 사용 하 여 메모리를 할당 합니다. 참조 [CHeapPtr](../../atl/reference/cheapptr-class.md) 및 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) 사용할 수 있는 방법에 대 한 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="a-nameccomheapptra--ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr  
 생성자입니다.  
  
```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pData`  
 기존 `CComHeapPtr` 개체입니다.  
  
### <a name="remarks"></a>주의  
 기존 힙 포인터를 만들 수 있습니다 `CComHeapPtr` 개체입니다. 그렇다면 새로운 `CComHeapPtr` 새 포인터 및 리소스 관리에 대 한 책임을 지지 하는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase 클래스](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator 클래스](../../atl/reference/ccomallocator-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

