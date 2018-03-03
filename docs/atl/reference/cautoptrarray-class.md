---
title: "CAutoPtrArray 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4afb07323cdb6b25914aabd802c4df73ee1d07c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray 클래스
이 클래스는 스마트 포인터의 배열을 만들 때 유용한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>매개 변수  
 `E`  
 포인터 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|생성자입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 생성자를 제공 하 고 메서드를 파생 [CAtlArray](../../atl/reference/catlarray-class.md) 및 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) 스마트 포인터를 저장 하는 컬렉션 클래스 개체 만들기를 지원할 수 있습니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray  
 생성자입니다.  
  
```
CAutoPtrArray() throw();
```  
  
### <a name="remarks"></a>설명  
 스마트 포인터 배열을 초기화합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlArray 클래스](../../atl/reference/catlarray-class.md)   
 [CAutoPtrElementTraits 클래스](../../atl/reference/cautoptrelementtraits-class.md)   
 [CAutoPtrList 클래스](../../atl/reference/cautoptrlist-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
