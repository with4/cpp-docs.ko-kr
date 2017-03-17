---
title: "CInterfaceList 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
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
ms.openlocfilehash: 50d86163080c5a0d0a7bb9ed6d77a40ac73722e7
ms.lasthandoff: 02/24/2017

---
# <a name="cinterfacelist-class"></a>CInterfaceList 클래스
이 클래스는 COM 인터페이스 포인터의 목록을 구성할 때 유용한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>매개 변수  
 `I`  
 저장에 대 한 포인터의 유형을 지정 하는 COM 인터페이스입니다.  
  
 `piid`  
 에 대 한 포인터의 IID `I`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|인터페이스 목록에 대 한 생성자입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 생성자 및 COM 인터페이스 포인터의 목록을 작성 하기 위한 파생 된 메서드를 제공 합니다. 사용 하 여 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 배열 필요한 경우.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="cinterfacelist"></a>CInterfaceList::CInterfaceList  
 인터페이스 목록에 대 한 생성자입니다.  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 블록 크기 기본값은 10입니다.  
  
### <a name="remarks"></a>주의  
 블록 크기는 새 요소를 필요할 때 할당 된 메모리의 양에 대비 합니다. 블록 크기가 클수록 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlList 클래스](../../atl/reference/catllist-class.md)   
 [CComQIPtr 클래스](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits 클래스](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

