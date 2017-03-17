---
title: "CAutoPtrArray 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 58ee329c7a3925fe3a29cf9738670cfa71df6777
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptrarray-class"></a>CAutoPtrArray 클래스
이 클래스는 스마트 포인터의 배열을 생성할 때 유용한 메서드를 제공 합니다.  
  
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
  
## <a name="remarks"></a>주의  
 이 클래스 생성자를 제공 하 고 메서드를 파생 [CAtlArray](../../atl/reference/catlarray-class.md) 및 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) 스마트 포인터를 저장 하는 컬렉션 클래스 개체의 생성을 지원 하기 위해.  
  
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
  
### <a name="remarks"></a>주의  
 스마트 포인터 배열을 초기화합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlArray 클래스](../../atl/reference/catlarray-class.md)   
 [CAutoPtrElementTraits 클래스](../../atl/reference/cautoptrelementtraits-class.md)   
 [CAutoPtrList 클래스](../../atl/reference/cautoptrlist-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

