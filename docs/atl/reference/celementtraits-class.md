---
title: "CElementTraits 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: 17
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
ms.sourcegitcommit: 6664a73967d3bdf9859556f21744737718018e74
ms.openlocfilehash: 8b7b91bd9e027a3946160d95da1199c24af3502d
ms.lasthandoff: 03/29/2017

---
# <a name="celementtraits-class"></a>CElementTraits 클래스
이 클래스는 복사, 이동, 비교 및 해싱 작업에 대 한 메서드 및 함수를 제공 하 여 컬렉션 클래스에 의해 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T>  
class CElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 컬렉션에 저장할 데이터의 형식입니다.  
  
## <a name="remarks"></a>설명  
 이 클래스는 이동, 복사, 비교, 및 컬렉션 클래스 개체에 저장 된 해시 요소에 대 한 기본 정적 함수 및 메서드를 제공 합니다. `CElementTraits`컬렉션 클래스를 통해 이러한 작업의 기본 공급자로 지정 [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), 및 [CRBTree](../../atl/reference/crbtree-class.md)합니다.  
  
 단순 데이터 형식에 대 한 기본 구현을 만으로도 충분 하지만 함수 및 메서드는 더 복잡 한 개체를 저장 하는 컬렉션 클래스를 사용 하면 사용자가 제공한 구현에 의해 재정의 해야 합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
## <a name="see-also"></a>참고 항목  
 [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

