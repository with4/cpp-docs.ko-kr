---
title: CRBTree 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b15ddf62545d5926faf75af760ed52219f1cb03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="crbtree-class"></a>CRBTree 클래스
이 클래스를 만들고 빨간색 검정 트리를 활용 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBTree
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
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CRBTree::KINARGTYPE](#kinargtype)|키를 입력 인수로 전달 될 때 사용 되는 형식입니다.|  
|[CRBTree::KOUTARGTYPE](#koutargtype)|키를 출력 인수로 반환 될 때 사용 되는 형식입니다.|  
|[CRBTree::VINARGTYPE](#vinargtype)|값은 입력 인수로 전달 되는 사용 되는 형식입니다.|  
|[CRBTree::VOUTARGTYPE](#voutargtype)|값을 출력 인수로 전달 될 때 사용 되는 형식입니다.|  
  
### <a name="public-classes"></a>public 클래스  
  
|이름|설명|  
|----------|-----------------|  
|[CRBTree::CPair 클래스](#cpair_class)|키 / 값 요소를 포함 하는 클래스입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRBTree:: ~ CRBTree](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|다음 사용 가능한 키를 사용 하는 요소의 위치를 찾으려면이 메서드를 호출 합니다.|  
|[CRBTree::GetAt](#getat)|트리에 지정 된 위치의 요소를 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetCount](#getcount)|트리에서 요소 수를 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetHeadPosition](#getheadposition)|트리의 헤드에 있는 요소에 대 한 위치 값을 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetKeyAt](#getkeyat)|트리에서 지정된 된 위치에서 키를 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetNext](#getnext)|이 메서드를 호출에 저장 된 요소에 대 한 포인터를 가져옵니다는 `CRBTree` 개체를 위치를 다음 요소로 이동 합니다.|  
|[CRBTree::GetNextAssoc](#getnextassoc)|키와 map에 저장 하는 요소의 값을 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|  
|[CRBTree::GetNextKey](#getnextkey)|트리에서 저장 된 요소 키를 얻기 위해이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|  
|[CRBTree::GetNextValue](#getnextvalue)|트리에 저장 된 요소의 값을 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|  
|[CRBTree::GetPrev](#getprev)|이 메서드를 호출에 저장 된 요소에 대 한 포인터를 가져옵니다는 `CRBTree` 개체를 다음 위치를 이전 요소로 업데이트 합니다.|  
|[CRBTree::GetTailPosition](#gettailposition)|요소 트리 꼬리에 대 한 위치 값을 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetValueAt](#getvalueat)|지정된 된 위치에 저장 된 값을 검색 하려면이 메서드를 호출 하는 `CRBTree` 개체입니다.|  
|[CRBTree::IsEmpty](#isempty)|이 메서드는 빈 트리 개체에 대 한 테스트를 호출 합니다.|  
|[CRBTree::RemoveAll](#removeall)|요소를 모두 제거 하려면이 메서드를 호출 하는 **CRBTree** 개체입니다.|  
|[CRBTree::RemoveAt](#removeat)|지정된 된 위치에 있는 요소를 제거 하려면이 메서드를 호출 하는 **CRBTree** 개체입니다.|  
|[CRBTree::SetValueAt](#setvalueat)|지정된 된 위치에 저장 된 값을 변경 하려면이 메서드를 호출 하는 `CRBTree` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 빨간색 검정 트리 추가 사용 하는 이진 검색을 트리는 약간의 정보가 유지 되는지 확인 하려면 노드당 "균형 조정,"를, 트리 높이 비례적 커질 및 성능에 영향을 하지 않습니다.  
  
 이 템플릿 클래스는에서 사용할 수 있도록 설계 [CRBMap](../../atl/reference/crbmap-class.md) 및 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)합니다. 이러한 파생된 클래스를 구성 하는 메서드는 대량의 제공한 `CRBTree`합니다.  
  
 다양 한 컬렉션 클래스 및 해당 기능 및 성능 특성의 자세한 논의 알려면 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="cpair_class"></a>  CRBTree::CPair 클래스  
 키 / 값 요소를 포함 하는 클래스입니다.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>설명  
 이 클래스의 메서드에 의해 사용 됩니다 [CRBTree::GetAt](#getat), [CRBTree::GetNext](#getnext), 및 [CRBTree::GetPrev](#getprev) 트리 구조에 저장 된 키 / 값 요소를 액세스할 수 있습니다.  
  
 멤버는 다음과 같습니다.  
  
|||  
|-|-|  
|`m_key`|키 요소 저장 하 고 데이터 멤버입니다.|  
|`m_value`|값 요소 저장 하 고 데이터 멤버입니다.|  
  
##  <a name="dtor"></a>  CRBTree:: ~ CRBTree  
 소멸자입니다.  
  
```
~CRBTree() throw();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다. 호출 [CRBTree::RemoveAll](#removeall) 를 모든 요소를 삭제 합니다.  
  
##  <a name="findfirstkeyafter"></a>  CRBTree::FindFirstKeyAfter  
 다음 사용 가능한 키를 사용 하는 요소의 위치를 찾으려면이 메서드를 호출 합니다.  
  
```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 키 값입니다.  
  
### <a name="return-value"></a>반환 값  
 사용 가능한 다음 키를 사용 하는 요소의 위치 값을 반환 합니다. 더 이상 요소가 없으면 NULL이 반환 됩니다.  
  
### <a name="remarks"></a>설명  
 이 방법을 사용 하면 트리를 이동할 위치 값을 미리 계산할 필요 없이 간편 합니다.  
  
##  <a name="getat"></a>  CRBTree::GetAt  
 트리에 지정 된 위치의 요소를 가져오려면이 메서드를 호출 합니다.  
  
```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 위치 값입니다.  
  
 `key`  
 키를 수신 하는 변수입니다.  
  
 *값*  
 값을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 처음 두 형식에 대 한 포인터를 반환 합니다.는 [CPair](#cpair_class)합니다. 세 번째 폼 키와 지정된 된 위치에 대 한 값을 가져옵니다.  
  
### <a name="remarks"></a>설명  
 위치 값 이전에 하 게 결정할 수는 방법에 대 한 호출 등 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::GetTailPosition](#gettailposition)합니다.  
  
 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `pos` NULL과 같습니다.  
  
##  <a name="getcount"></a>  CRBTree::GetCount  
 트리에서 요소 수를 가져오려면이 메서드를 호출 합니다.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 (각 키/값 쌍 하나 이상의 요소가)에 저장 된 요소의 트리 수를 반환 합니다.  
  
##  <a name="getheadposition"></a>  CRBTree::GetHeadPosition  
 트리의 헤드에 있는 요소에 대 한 위치 값을 가져오려면이 메서드를 호출 합니다.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 트리의 헤드에 있는 요소에 대 한 위치 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 반환한 값 `GetHeadPosition` 와 같은 메서드와 함께 사용할 수 있습니다 [CRBTree::GetKeyAt](#getkeyat) 또는 [CRBTree::GetNext](#getnext) 하 트리를 탐색 하 고 값을 검색 합니다.  
  
##  <a name="getkeyat"></a>  CRBTree::GetKeyAt  
 트리에서 지정된 된 위치에서 키를 가져오려면이 메서드를 호출 합니다.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 위치 값입니다.  
  
### <a name="return-value"></a>반환 값  
 위치에 저장 된 키를 반환 `pos` 트리에서 합니다.  
  
### <a name="remarks"></a>설명  
 경우 `pos` 올바른 위치 값이 아닌 결과 예측할 수 없습니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `pos` NULL과 같습니다.  
  
##  <a name="getnext"></a>  CRBTree::GetNext  
 이 메서드를 호출에 저장 된 요소에 대 한 포인터를 가져옵니다는 `CRBTree` 개체를 위치를 다음 요소로 이동 합니다.  
  
```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 와 같은 메서드에 대 한 이전 호출에서 반환 하는 위치 카운터 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.  
  
### <a name="return-value"></a>반환 값  
 다음에 대 한 포인터를 반환 [CPair](#cpair_class) 트리에서 값입니다.  
  
### <a name="remarks"></a>설명  
 `pos` 위치 카운터는 각 호출 후 업데이트 됩니다. 검색 된 요소가 트리에서 마지막 면 `pos` NULL로 설정 됩니다.  
  
##  <a name="getnextassoc"></a>  CRBTree::GetNextAssoc  
 키와 map에 저장 하는 요소의 값을 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 와 같은 메서드에 대 한 이전 호출에서 반환 하는 위치 카운터 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.  
  
 `key`  
 템플릿 매개 변수를 트리의 키의 형식을 지정 합니다.  
  
 *값*  
 템플릿 매개 변수를 트리의 값의 형식을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 `pos` 위치 카운터는 각 호출 후 업데이트 됩니다. 검색 된 요소가 트리에서 마지막 면 `pos` NULL로 설정 됩니다.  
  
##  <a name="getnextkey"></a>  CRBTree::GetNextKey  
 트리에서 저장 된 요소 키를 얻기 위해이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 와 같은 메서드에 대 한 이전 호출에서 반환 하는 위치 카운터 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.  
  
### <a name="return-value"></a>반환 값  
 트리에서 다음 키에 대 한 참조를 반환합니다.  
  
### <a name="remarks"></a>설명  
 현재 위치 카운터 업데이트 `pos`합니다. 트리에서 엔트리를 더 이상 없으면 위치 카운터 NULL로 설정 됩니다.  
  
##  <a name="getnextvalue"></a>  CRBTree::GetNextValue  
 트리에 저장 된 요소의 값을 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.  
  
```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 와 같은 메서드에 대 한 이전 호출에서 반환 하는 위치 카운터 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.  
  
### <a name="return-value"></a>반환 값  
 트리에서 다음 값에 대 한 참조를 반환합니다.  
  
### <a name="remarks"></a>설명  
 현재 위치 카운터 업데이트 `pos`합니다. 트리에서 엔트리를 더 이상 없으면 위치 카운터 NULL로 설정 됩니다.  
  
##  <a name="getprev"></a>  CRBTree::GetPrev  
 이 메서드를 호출에 저장 된 요소에 대 한 포인터를 가져옵니다는 `CRBTree` 개체를 다음 위치를 이전 요소로 업데이트 합니다.  
  
```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 와 같은 메서드에 대 한 이전 호출에서 반환 하는 위치 카운터 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 대 한 포인터를 반환 [CPair](#cpair_class) 트리에서 저장 된 값입니다.  
  
### <a name="remarks"></a>설명  
 현재 위치 카운터 업데이트 `pos`합니다. 트리에서 엔트리를 더 이상 없으면 위치 카운터 NULL로 설정 됩니다.  
  
##  <a name="gettailposition"></a>  CRBTree::GetTailPosition  
 요소 트리 꼬리에 대 한 위치 값을 가져오려면이 메서드를 호출 합니다.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 요소 트리 꼬리에 대 한 위치 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 반환한 값 `GetTailPosition` 와 같은 메서드와 함께 사용할 수 있습니다 [CRBTree::GetKeyAt](#getkeyat) 또는 [CRBTree::GetPrev](#getprev) 하 트리를 탐색 하 고 값을 검색 합니다.  
  
##  <a name="getvalueat"></a>  CRBTree::GetValueAt  
 지정된 된 위치에 저장 된 값을 검색 하려면이 메서드를 호출 하는 `CRBTree` 개체입니다.  
  
```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 와 같은 메서드에 대 한 이전 호출에서 반환 하는 위치 카운터 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 위치에 저장 된 값에 대 한 참조를 반환 합니다.는 `CRBTree` 개체입니다.  
  
##  <a name="isempty"></a>  CRBTree::IsEmpty  
 이 메서드는 빈 트리 개체에 대 한 테스트를 호출 합니다.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 트리 비어 있으면 **false** 그렇지 않은 경우.  
  
##  <a name="kinargtype"></a>  CRBTree::KINARGTYPE  
 키를 입력 인수로 전달 될 때 사용 되는 형식입니다.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>  CRBTree::KOUTARGTYPE  
 키를 출력 인수로 반환 될 때 사용 되는 형식입니다.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="removeall"></a>  CRBTree::RemoveAll  
 요소를 모두 제거 하려면이 메서드를 호출 하는 `CRBTree` 개체입니다.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>설명  
 지웁니다는 `CRBTree` 개체에 요소를 저장 하는 데 사용 된 메모리를 해제 합니다.  
  
##  <a name="removeat"></a>  CRBTree::RemoveAt  
 지정된 된 위치에 있는 요소를 제거 하려면이 메서드를 호출 하는 **CRBTree** 개체입니다.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 와 같은 메서드에 대 한 이전 호출에서 반환 하는 위치 카운터 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 위치에 저장 된 키/값 쌍을 제거 합니다. 요소를 저장 하는 데 사용 된 메모리가 해제 됩니다. 위치에서 참조 `pos` 무효화 되 고 트리에 다른 요소의 위치 반드시 그럴 유효한 상태를 유지 하는 동안 유지 순서와 동일 합니다.  
  
##  <a name="setvalueat"></a>  CRBTree::SetValueAt  
 지정된 된 위치에 저장 된 값을 변경 하려면이 메서드를 호출 하는 `CRBTree` 개체입니다.  
  
```
void SetValueAt(POSITION pos, VINARGTYPE value);
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 와 같은 메서드에 대 한 이전 호출에서 반환 하는 위치 카운터 [CRBTree::GetHeadPosition](#getheadposition) 또는 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.  
  
 *값*  
 에 추가할 값의 `CRBTree` 개체입니다.  
  
### <a name="remarks"></a>설명  
 Value 요소에 지정된 된 위치에 저장 된 변경의 `CRBTree` 개체입니다.  
  
##  <a name="vinargtype"></a>  CRBTree::VINARGTYPE  
 값은 입력 인수로 전달 되는 사용 되는 형식입니다.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>  CRBTree::VOUTARGTYPE  
 값을 출력 인수로 전달 될 때 사용 되는 형식입니다.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
