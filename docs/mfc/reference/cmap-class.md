---
title: "CMap 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- dictionary mapping class
- collection classes, dictionary mapping
- CMap class
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
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
ms.openlocfilehash: 680d44fe6154861d2c638697cfc9d3fbeab36cc4
ms.lasthandoff: 02/24/2017

---
# <a name="cmap-class"></a>CMap 클래스
고유 키를 값에 매핑하는 사전 컬렉션 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>매개 변수  
 `KEY`  
 지도 키로 사용 되는 개체의 클래스입니다.  
  
 `ARG` *_* `KEY`  
 데이터 형식에 사용 되는 `KEY` 인수에 대 한 참조, 대개 `KEY`합니다.  
  
 `VALUE`  
 Map에 저장 하는 개체의 클래스입니다.  
  
 `ARG` *_* `VALUE`  
 데이터 형식에 사용 되는 `VALUE` 인수에 대 한 참조, 대개 `VALUE`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-structures"></a>공용 구조체  
  
|이름|설명|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|키 값과 연결된 된 개체의 값을 포함 하는 중첩 된 구조입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|키 값에 매핑하는 컬렉션을 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|이 map의 요소 수를 반환합니다.|  
|[CMap::GetHashTableSize](#gethashtablesize)|해시 테이블의 요소 수를 반환합니다.|  
|[CMap::GetNextAssoc](#getnextassoc)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CMap::GetSize](#getsize)|이 map의 요소 수를 반환합니다.|  
|[CMap::GetStartPosition](#getstartposition)|첫 번째 요소의 위치를 반환합니다.|  
|[CMap::InitHashTable](#inithashtable)|해시 테이블을 초기화 하 고 크기를 지정 합니다.|  
|[CMap::IsEmpty](#isempty)|빈 맵 조건 (요소 없음)에 대해 테스트 합니다.|  
|[CMap::Lookup](#lookup)|지정된 된 키에 매핑된 값을 조회 합니다.|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|첫 번째 요소에 대 한 포인터를 반환합니다.|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|다음 요소를 반복 하는 데 대 한 포인터를 가져옵니다.|  
|[CMap::PLookup](#plookup)|지정된 된 값을 일치 하는 값을 갖는 키에 대 한 포인터를 반환 합니다.|  
|[CMap::RemoveAll](#removeall)|이 맵에서 모든 요소를 제거합니다.|  
|[CMap::RemoveKey](#removekey)|키가 지정 된 요소를 제거 합니다.|  
|[CMap::SetAt](#setat)|Map에 요소를 삽입합니다. 일치 하는 키가 있을 경우에 기존 요소를 대체 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CMap::operator]](#operator_at)|지도 â €에 요소를 삽입 "에 대 한 연산자 대체 `SetAt`합니다.|  
  
## <a name="remarks"></a>주의  
 Map에는 키-값 쌍 (요소)를 삽입 하면 효율적으로 검색 하거나 액세스 키를 사용 하는 쌍을 삭제할 수 있습니다. 지도에 있는 모든 요소를 반복할 수도 있습니다.  
  
 형식의 변수 **위치** 항목에 대 한 대체 액세스에 사용 됩니다. 사용할 수는 **위치** 항목 "기억" 하 고 맵을 통해 반복 합니다. 이 반복; 키 값으로 순차적 임을 생각할 수 있습니다. 아닙니다. 검색 된 요소의 순서는 결정 되지 않습니다.  
  
 대부분의 사용에 대 한 사용자 지정 되어야 글로벌 도우미 함수는이 클래스 호출의 특정 멤버 함수는 `CMap` 클래스입니다. 참조 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) 의 매크로 및 전역 섹션에는 `MFC``Reference`합니다.  
  
 `CMap`재정의 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) serialization 및 요소 덤프를 지원 하도록 합니다. 맵을 사용 하 여 보관 파일에 저장 되는 경우 `Serialize`, 각 지도 요소 차례로 serialize 됩니다. 기본 구현에서 `SerializeElements` 도우미 함수는 비트 쓰기를 수행 합니다. 파생 된 포인터 컬렉션 항목의 serialization에 대 한 내용은 `CObject` 다른 사용자 정의 형식 참조 또는 [하는 방법: 형식이 안전한 컬렉션을 만드는](../../mfc/how-to-make-a-type-safe-collection.md)합니다.  
  
 맵 (키와 값)에 있는 개별 요소의 진단 덤프, 필요한 경우 덤프 컨텍스트 깊이 1 이상으로 설정 해야 합니다.  
  
 경우는 `CMap` 개체를 삭제 하거나 해당 요소를 제거 하 고, 키 및 값 제거 됩니다.  
  
 맵 클래스를 파생 목록 파생 하는 것과 비슷합니다. 문서를 참조 하십시오 [컬렉션](../../mfc/collections.md) 특수 한 용도의 목록 클래스의 파생에 대 한 예제입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtempl.h  
  
##  <a name="cmap"></a>CMap::CMap  
 빈 맵을 생성합니다.  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 지도 확장 하는 것에 대 한 메모리 할당 세분성을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 메모리의 단위에서 할당 되는 지도 늘어나면 `nBlockSize` 항목입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections #&56;](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="cpair"></a>CMap::CPair  
 키 값과 연결된 된 개체의 값을 포함합니다.  
  
### <a name="remarks"></a>주의  
 이 클래스 내에서 중첩된 구조 [CMap](../../mfc/reference/cmap-class.md)합니다.  
  
 구조는 두 가지 필드로 구성 됩니다.  
  
- **keyÂ Â Â** 키 형식의 실제 값입니다.  
  
- **valueÂ Â Â** 연결된 된 개체의 값입니다.  
  
 반환 값을 저장 하는 데 사용 됩니다 [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), 및 [CMap::PGetNextAssoc](#pgetnextassoc)합니다.  
  
### <a name="example"></a>예제  
 사용의 예에 대 한 예제를 참조 하십시오. [CMap::PLookup](#plookup)합니다.  
  
##  <a name="getcount"></a>CMap::GetCount  
 Map의 요소 수를 검색 합니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 요소의 수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CMap::Lookup](#lookup)합니다.  
  
##  <a name="gethashtablesize"></a>CMap::GetHashTableSize  
 지도 대 한 해시 테이블에 있는 요소의 수를 결정합니다.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 해시 테이블에 있는 요소의 수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections #&57;](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
##  <a name="getnextassoc"></a>CMap::GetNextAssoc  
 에 지도 요소를 검색 `rNextPosition`, 그런 다음 업데이트 `rNextPosition` 맵에서 다음 요소를 참조 하 합니다.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `rNextPosition`  
 에 대 한 참조를 지정 된 **위치** 이전에서 반환 된 값 `GetNextAssoc` 또는 `GetStartPosition` 호출 합니다.  
  
 *키*  
 Map의 키의 형식을 지정 하는 템플릿 매개 변수  
  
 `rKey`  
 검색 된 요소의 반환 된 키를 지정합니다.  
  
 *값*  
 Map의 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `rValue`  
 검색 된 요소의 반환 된 값을 지정합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 지도에 있는 모든 요소를 통해 반복 하는 데 가장 유용 합니다. 않음을 유의 하십시오 위치 시퀀스 반드시 키 값 시퀀스와 동일 합니다.  
  
 검색 된 요소가 있으면 지도 마지막 다음의 새 값 `rNextPosition` 로 설정 된 **NULL**합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CMap::SetAt](#setat)합니다.  
  
##  <a name="getsize"></a>CMap::GetSize  
 지도 요소 수를 반환합니다.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 지도 있는 항목의 수입니다.  
  
### <a name="remarks"></a>주의  
 Map의 요소 수를 검색 하려면이 메서드를 호출 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections #&58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CMap::GetStartPosition  
 가 반환 하 여 지도 반복을 시작할는 **위치** 에 전달 될 수 있는 값을 `GetNextAssoc` 를 호출 합니다.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 지도; 반복 하기 위한 시작 위치를 나타내는 값 또는 **NULL** 맵이 비어 있는 경우.  
  
### <a name="remarks"></a>주의  
 반복 시퀀스는 예측할 수 없습니다. 따라서 "첫 번째 요소는 맵에서" 특별 한 의미가 없습니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CMap::SetAt](#setat)합니다.  
  
##  <a name="inithashtable"></a>CMap::InitHashTable  
 해시 테이블을 초기화합니다.  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUEÂ);  
```  
  
### <a name="parameters"></a>매개 변수  
 `hashSize`  
 해시 테이블의 항목 수입니다.  
  
 `bAllocNow`  
 경우 **TRUE**, 초기화, 해시 테이블을 할당 필요할 때 테이블 할당은 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 최상의 성능을 얻으려면 해시 테이블 크기 소수 이어야 합니다. 충돌을 최소화 하려면 크기 해야 약 20%는 가장 큰 예상된 데이터 집합 보다 큰 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CMap::Lookup](#lookup)합니다.  
  
##  <a name="isempty"></a>CMap::IsEmpty  
 맵이 비어 있는지 여부를 결정 합니다.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 맵은; 요소가 없으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CMap::RemoveAll](#removeall)합니다.  
  
##  <a name="lookup"></a>CMap::Lookup  
 지정된 된 키에 매핑된 값을 조회 합니다.  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `ARG_KEY`  
 템플릿 매개 변수 유형을 지정 하는 `key` 값입니다.  
  
 `key`  
 조회 되는 요소를 식별 하는 키를 지정 합니다.  
  
 *값*  
 조회 되는 값의 형식을 지정 합니다.  
  
 `rValue`  
 조회 값을 받습니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 발견 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 `Lookup`해싱 알고리즘을를 사용 하 여 신속 하 게 정확 하 게 지정된 된 키와 일치 하는 키가 있는 지도 요소를 찾습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections #&58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="operator_at"></a>CMap::operator]  
 에 대 한 편리한 대체는 `SetAt` 멤버 함수입니다.  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>매개 변수  
 *값*  
 지도 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `ARG_KEY`  
 키 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `key`  
 지도에서 값을 검색 하는 데 사용 된 키입니다.  
  
### <a name="remarks"></a>주의  
 따라서 (l-value) 대입문의 왼쪽에만 사용할 수 있습니다. 지정된 된 키와 지도 요소가 이면 새 요소가 만들어집니다.  
  
 경우 없습니다 "오른쪽" (r-value)이이 운영자에 해당 하는 지도에서 키를 찾을 수 있습니다 가능성이 있기 때문에 사용 하 여 `Lookup` 요소 검색을 위한 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CMap::Lookup](#lookup)합니다.  
  
##  <a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 Map 개체의 첫 번째 항목을 반환합니다.  
  
```  
const CPair* PGetFirstAssoc() const;Â CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>반환 값  
 지도;의 첫 번째 항목에 대 한 포인터 참조 [CMap::CPair](#cpair)합니다. 지도 항목이 없는 경우이 값은 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 Map 개체에 대 한 포인터는 첫 번째 요소를 반환 하려면이 함수를 호출 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections #&59;](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 가 가리키는 지도 요소를 검색 `pAssocRec`합니다.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAssocRet*  
 이전에서 반환 된 맵 항목을 가리키는 [PGetNextAssoc](#pgetnextassoc) 또는 [CMap::PGetFirstAssoc](#pgetfirstassoc) 를 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 맵에 표시 합니다; 다음 항목에 대 한 포인터 참조 [CMap::CPair](#cpair)합니다. 값은 해당 요소가 맵에 마지막 이면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 지도에 있는 모든 요소를 반복 하려면이 메서드를 호출 합니다. 호출 하 여 첫 번째 요소를 검색 `PGetFirstAssoc` 다음 지도에 연속적으로 호출 될 때까지 반복 `PGetNextAssoc`합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CMap::PGetFirstAssoc](#pgetfirstassoc)합니다.  
  
##  <a name="plookup"></a>CMap::PLookup  
 지정된 된 키에 매핑된 값을 찾습니다.  
  
```  
const CPair* PLookup(ARG_KEY  key) const;
CPair* PLookup(Â    ARG_KEY  keyÂ);  ```  
  
### Parameters  
 `key`  
 Key for the element to be searched for.  
  
### Return Value  
 A pointer to a key structure; see [CMap::CPair](#cpair). If no match is found, `CMap::PLookup` returns `NULL`.  
  
### Remarks  
 Call this method to search for a map element with a key that exactly matches the given key.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>  CMap::RemoveAll  
 Removes all the values from this map by calling the global helper function **DestructElements**.  
  
```  
void RemoveAll();
```  
  
### Remarks  
 The function works correctly if the map is already empty.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>  CMap::RemoveKey  
 Looks up the map entry corresponding to the supplied key; then, if the key is found, removes the entry.  
  
```  
BOOL RemoveKey(ARG_KEY key);
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the key.  
  
 `key`  
 Key for the element to be removed.  
  
### Return Value  
 Nonzero if the entry was found and successfully removed; otherwise 0.  
  
### Remarks  
 The **DestructElements** helper function is used to remove the entry.  
  
### Example  
 See the example for [CMap::SetAt](#setat).  
  
##  <a name="setat"></a>  CMap::SetAt  
 The primary means to insert an element in a map.  
  
```  
void SetAt (ARG_KEY 키, ARG_VALUE newValue);
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the `key` parameter.  
  
 `key`  
 Specifies the key of the new element.  
  
 `ARG_VALUE`  
 Template parameter specifying the type of the `newValue` parameter.  
  
 `newValue`  
 Specifies the value of the new element.  
  
### Remarks  
 First, the key is looked up. If the key is found, then the corresponding value is changed; otherwise a new key-value pair is created.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## See Also  
 [MFC Sample COLLECT](../../visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)  

