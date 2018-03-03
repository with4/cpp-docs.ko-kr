---
title: "CInterfaceList 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bd8817b325ebb9a9d8899211416dcbecfcd3f79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
 저장할 수에 대 한 포인터의 유형을 지정 하는 COM 인터페이스입니다.  
  
 `piid`  
 IID에 대 한 포인터 `I`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|인터페이스 목록에 대 한 생성자입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 생성자 및 COM 인터페이스 포인터의 목록을 생성 하기 위한 파생된 메서드를 제공 합니다. 사용 하 여 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 때 배열이 필요 합니다.  
  
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
  
### <a name="remarks"></a>설명  
 블록 크기는 새 요소가 필요한 경우 할당 된 메모리의 업무량을 측정 합니다. 블록 크기는 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 하 여 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlList 클래스](../../atl/reference/catllist-class.md)   
 [CComQIPtr 클래스](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits 클래스](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
