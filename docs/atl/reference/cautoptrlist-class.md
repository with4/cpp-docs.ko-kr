---
title: "CAutoPtrList 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0887b0fdaeeaf498bacdc5eec66981656f34fed8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
  
## <a name="remarks"></a>설명  
 이 클래스는 생성자를 제공 하 고 메서드를 파생 [CAtlList](../../atl/reference/catllist-class.md) 및 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) 스마트 포인터를 저장 하는 목록 개체 만들기를 지원할 수 있습니다. 클래스 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 배열 개체에 대 한 유사한 기능을 제공 합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CAutoPtrList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="cautoptrlist"></a>CAutoPtrList::CAutoPtrList  
 생성자입니다.  
  
```
CAutoPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 블록 크기 기본값은 10입니다.  
  
### <a name="remarks"></a>설명  
 블록 크기는 새 요소가 필요한 경우 할당 된 메모리의 업무량을 측정 합니다. 블록 크기는 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 하 여 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlList 클래스](../../atl/reference/catllist-class.md)   
 [CAutoPtrElementTraits 클래스](../../atl/reference/cautoptrelementtraits-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
