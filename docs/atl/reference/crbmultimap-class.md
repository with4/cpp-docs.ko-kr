---
title: CRBMultiMap 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
dev_langs:
- C++
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ec016df268b702fd8b26d742d702ac38b95fa06
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365193"
---
# <a name="crbmultimap-class"></a>CRBMultiMap 클래스
이 클래스는 각 키 빨간색 검정 이진 트리를 사용 하 여 둘 이상의 값에 연결할 수 있게 하는 매핑 구조를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename K,
         typename V, 
         class KTraits = CElementTraits<K>, 
         class VTraits = CElementTraits<V>>  
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|생성자입니다.|  
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|지정된 된 키와 첫 번째 요소의 위치를 찾으려면이 메서드를 호출 합니다.|  
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|지정된 된 키와 연결 된 값을 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.|  
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|지정된 된 키와 연결 된 요소를 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.|  
|[CRBMultiMap::Insert](#insert)|지도에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.|  
|[CRBMultiMap::RemoveKey](#removekey)|지정된 된 키에 대 한 키/값 요소를 모두 제거 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 `CRBMultiMap` 요소 키와 값의 순서 있는 배열 관리 지정 된 형식의 매핑 배열에 대 한 지원을 제공 합니다. 와 달리는 [CRBMap](../../atl/reference/crbmap-class.md) 클래스, 각 키 값이 여러 개 연결 될 수 있습니다.  
  
 (키와 값의 구성) 하는 요소는 이진 트리에 저장 된 구조를 사용 하는 [CRBMultiMap::Insert](#insert) 메서드. 사용 하 여 요소를 제거할 수는 [CRBMultiMap::RemoveKey](#removekey) 메서드를 지정 된 키와 일치 하는 모든 요소를 삭제 합니다.  
  
 트리를 트래버스하는 있기 때문 메서드로 같은 [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), 및 [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)합니다. 에 액세스 하는 키 하나에 잠재적으로 여러 값은 가능한을 사용 하는 [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), 및 [CRBMultiMap::GetNextWithKey ](#getnextwithkey) 메서드. 예를 참조 [CRBMultiMap::CRBMultiMap](#crbmultimap) 실제로는 예시용입니다.  
  
 `KTraits` 및 `VTraits` 매개 변수는 복사 하거나 요소를 이동 하는 데 필요한 모든 추가 코드를 포함 하는 특성 클래스입니다.  
  
 `CRBMultiMap` 파생 된 [CRBTree](../../atl/reference/crbtree-class.md), 빨강 검정 알고리즘을 사용 하 여 이진 트리를 구현 하는 합니다. 에 대 한 대안 `CRBMultiMap` 및 `CRBMap` 에서 제공 하는 [CAtlMap](../../atl/reference/catlmap-class.md) 클래스입니다. 사용 하는 소수의 요소를 저장 해야 하는 경우 고려는 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스를 대신 합니다.  
  
 다양 한 컬렉션 클래스 및 해당 기능 및 성능 특성의 자세한 논의 알려면 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="crbmultimap"></a>  CRBMultiMap::CRBMultiMap  
 생성자입니다.  
  
```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 블록 크기입니다.  
  
### <a name="remarks"></a>설명  
 `nBlockSize` 매개 변수는 새 요소가 필요한 경우 할당 된 메모리 양 측정 합니다. 블록 크기는 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 하 여 합니다. 기본값 한 번에 10 개의 요소에 대 한 공간을 할당 합니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]  
  
##  <a name="dtor"></a>  CRBMultiMap:: ~ CRBMultiMap  
 소멸자입니다.  
  
```
~CRBMultiMap() throw();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
##  <a name="findfirstwithkey"></a>  CRBMultiMap::FindFirstWithKey  
 지정된 된 키와 첫 번째 요소의 위치를 찾으려면이 메서드를 호출 합니다.  
  
```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 찾을 요소를 식별 하는 키를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 키가 있으면 NULL 그렇지 않으면 첫 번째 키/값 요소 위치를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 키에는 `CRBMultiMap` 하나 이상의 연결 된 값을 가질 수 있습니다. 이 메서드는 해당 특정 키와 연결 된 첫 번째 값 (있을 수 있음, 실제로 유일한 값)의 위치 값을 제공 합니다. 반환 되는 위치 값으로 사용할 수 있습니다 [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) 또는 [CRBMultiMap::GetNextWithKey](#getnextwithkey) 하 값을 확인 하 고 위치를 업데이트 합니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRBMultiMap::CRBMultiMap](#crbmultimap)합니다.  
  
##  <a name="getnextvaluewithkey"></a>  CRBMultiMap::GetNextValueWithKey  
 지정된 된 키와 연결 된 값을 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.  
  
```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 호출을 사용 하 여 얻은 위치 값 [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) 또는 [CRBMultiMap::GetNextWithKey](#getnextwithkey), 또는 이전에 호출 `GetNextValueWithKey`합니다.  
  
 `key`  
 찾을 요소를 식별 하는 키를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 키와 연결 된 요소 쌍을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 위치 값은 키와 관련 된 다음 값을 가리키도록 업데이트 됩니다. 값이 더 이상 없으면 위치 값은 NULL로 설정 됩니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRBMultiMap::CRBMultiMap](#crbmultimap)합니다.  
  
##  <a name="getnextwithkey"></a>  CRBMultiMap::GetNextWithKey  
 지정된 된 키와 연결 된 요소를 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.  
  
```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 호출을 사용 하 여 얻은 위치 값 [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) 또는 [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), 또는 이전에 호출 `GetNextWithKey`합니다.  
  
 `key`  
 찾을 요소를 식별 하는 키를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 다음 반환 [CRBTree::CPair 클래스](crbtree-class.md#cpair_class) 지정된 된 키와 연결 된 요소입니다.  
  
### <a name="remarks"></a>설명  
 위치 값은 키와 관련 된 다음 값을 가리키도록 업데이트 됩니다. 값이 더 이상 없으면 위치 값은 NULL로 설정 됩니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
##  <a name="insert"></a>  CRBMultiMap::Insert  
 지도에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.  
  
```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 에 추가할 키 값은 `CRBMultiMap` 개체입니다.  
  
 *값*  
 에 추가할 값의 `CRBMultiMap` 와 연결 된 개체 `key`합니다.  
  
### <a name="return-value"></a>반환 값  
 에 있는 키/값 요소 쌍의 위치를 반환 하는 `CRBMultiMap` 개체입니다.  
  
### <a name="remarks"></a>설명  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRBMultiMap::CRBMultiMap](#crbmultimap)합니다.  
  
##  <a name="removekey"></a>  CRBMultiMap::RemoveKey  
 지정된 된 키에 대 한 키/값 요소를 모두 제거 하려면이 메서드를 호출 합니다.  
  
```
size_t RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 삭제 될 요소를 식별 하는 키를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 키와 연결 된 값의 수를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 `RemoveKey` 일치 하는 키가 있는 키/값 요소를 모두 삭제 `key`합니다.  
  
 기본 클래스에 대 한 설명서를 참조 하십시오. [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 내용은 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRBMultiMap::CRBMultiMap](#crbmultimap)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRBTree 클래스](../../atl/reference/crbtree-class.md)   
 [CAtlMap 클래스](../../atl/reference/catlmap-class.md)   
 [CRBMap 클래스](../../atl/reference/crbmap-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
