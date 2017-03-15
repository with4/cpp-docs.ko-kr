---
title: "CAutoPtrList 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAutoPtrList
- CAutoPtrList
- ATL.CAutoPtrList
- ATL::CAutoPtrList<E>
- ATL.CAutoPtrList<E>
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
caps.latest.revision: 20
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
ms.openlocfilehash: b39c3c08cf2970036bf8690c46a4f3518a7a55e1
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptrlist-class"></a>CAutoPtrList 클래스
이 클래스는 스마트 포인터의 목록을 구성할 때 유용한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename E>  
class CAutoPtrList : 
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>매개 변수  
 `E`  
 포인터 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|생성자입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스 생성자를 제공 하 고 메서드를 파생 [CAtlList](../../atl/reference/catllist-class.md) 및 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) 스마트 포인터를 저장 하는 목록 개체의 생성을 지원 하기 위해. 클래스 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 배열 개체에 대 한 비슷한 기능을 제공 합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CAutoPtrList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="a-namecautoptrlista--cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a>CAutoPtrList::CAutoPtrList  
 생성자입니다.  
  
```
CAutoPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 블록 크기 기본값은 10입니다.  
  
### <a name="remarks"></a>주의  
 블록 크기는 새 요소를 필요할 때 할당 된 메모리의 양에 대비 합니다. 블록 크기가 클수록 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlList 클래스](../../atl/reference/catllist-class.md)   
 [CAutoPtrElementTraits 클래스](../../atl/reference/cautoptrelementtraits-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

