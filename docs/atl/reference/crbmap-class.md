---
title: "CRBMap 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cfa4d6fff6b46341f01b4d5ce18d9ec418738bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="crbmap-class"></a>CRBMap 클래스
이 클래스에는 빨간색 검정 이진 트리를 사용 하 여 매핑 구조를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
```    
  
#### <a name="parameters"></a>매개 변수  
 `K`  
 중요 한 요소 형식입니다.  
  
 *V*  
 값 요소 형식입니다.  
  
 `KTraits`  
 복사 또는 주요 요소를 이동 하는 데 사용 되는 코드입니다. 참조 [CElementTraits 클래스](../../atl/reference/celementtraits-class.md) 내용을 확인 합니다.  
  
 `VTraits`  
 값 요소 이동 하거나 복사 하는 데 사용 되는 코드입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRBMap::CRBMap](#crbmap)|생성자입니다.|  
|[CRBMap:: ~ CRBMap](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRBMap::Lookup](#lookup)|키 또는 값을 조회 하려면이 메서드를 호출 하는 `CRBMap` 개체입니다.|  
|[CRBMap::RemoveKey](#removekey)|요소를 제거 하려면이 메서드를 호출 하는 `CRBMap` 키가 지정 된 개체입니다.|  
|[CRBMap::SetAt](#setat)|지도에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 `CRBMap`관리 되는 주요 요소와 연결 된 값의 순서 있는 배열 지정 된 형식의 매핑 배열에 대 한 지원을 제공 합니다. 각 키에 연결 된 값이 하나만 있을 수 있습니다. (키와 값의 구성) 하는 요소는 이진 트리에 저장 된 구조를 사용 하는 [CRBMap::SetAt](#setat) 메서드. 사용 하 여 요소를 제거할 수는 [CRBMap::RemoveKey](#removekey) 메서드를 지정 된 키 값을 가진 요소를 삭제 합니다.  
  
 트리를 트래버스하는 있기 때문 메서드로 같은 [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), 및 [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)합니다.  
  
 `KTraits` 및 `VTraits` 매개 변수는 복사 하거나 요소를 이동 하는 데 필요한 모든 추가 코드를 포함 하는 특성 클래스입니다.  
  
 `CRBMap`파생 된 [CRBTree](../../atl/reference/crbtree-class.md), 빨강 검정 알고리즘을 사용 하 여 이진 트리를 구현 하는 합니다. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) 은 각 키에 대 한 여러 값을 허용 하는 변형입니다. 파생 너무 `CRBTree`와 많은 기능을 공유 하므로 `CRBMap`합니다.  
  
 둘 다에 대 한 대안 `CRBMap` 및 `CRBMultiMap` 에서 제공 된 [CAtlMap](../../atl/reference/catlmap-class.md) 클래스. 사용 하는 소수의 요소를 저장 해야 하는 경우 고려는 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스를 대신 합니다.  
  
 다양 한 컬렉션 클래스 및 해당 기능 및 성능 특성의 자세한 논의 알려면 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="crbmap"></a>CRBMap::CRBMap  
 생성자입니다.  
  
```
explicit CRBMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 블록 크기입니다.  
  
### <a name="remarks"></a>설명  
 `nBlockSize` 매개 변수는 새 요소가 필요한 경우 할당 된 메모리 양 측정 합니다. 블록 크기는 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 하 여 합니다. 기본값 한 번에 10 개의 요소에 대 한 공간을 할당 합니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]  
  
##  <a name="dtor"></a>CRBMap:: ~ CRBMap  
 소멸자입니다.  
  
```
~CRBMap() throw();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
##  <a name="lookup"></a>CRBMap::Lookup  
 키 또는 값을 조회 하려면이 메서드를 호출 하는 `CRBMap` 개체입니다.  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 조회 되는 요소를 식별 하는 키를 지정 합니다.  
  
 *값*  
 조회 값을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드의 첫 번째 형태는 키 발견 되 면 true, 그렇지 않으면 false를 반환 합니다. 에 대 한 포인터를 반환 하는 두 번째 및 세 번째 형태는 [CPair](crbtree-class.md#cpair_class)합니다.  
  
### <a name="remarks"></a>설명  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]  
  
##  <a name="removekey"></a>CRBMap::RemoveKey  
 요소를 제거 하려면이 메서드를 호출 하는 `CRBMap` 키가 지정 된 개체입니다.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 제거 하려는 키에 해당 하는 요소 쌍입니다.  
  
### <a name="return-value"></a>반환 값  
 검색 및 제거, 실패 한 경우 false가 있으면 true를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]  
  
##  <a name="setat"></a>CRBMap::SetAt  
 지도에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 에 추가할 키 값은 `CRBMap` 개체입니다.  
  
 *값*  
 에 추가할 값의 `CRBMap` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 있는 키/값 요소 쌍의 위치를 반환 하는 `CRBMap` 개체입니다.  
  
### <a name="remarks"></a>설명  
 `SetAt`일치 하는 키가 있을 경우 기존 요소를 바꿉니다. 키가 없는 경우 새 키/값 쌍이 만들어집니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CRBTree 클래스](../../atl/reference/crbtree-class.md)   
 [CAtlMap 클래스](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap 클래스](../../atl/reference/crbmultimap-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
