---
title: "CSimpleMap 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
dev_langs: C++
helpviewer_keywords: CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 998001954d24d100fefb18e3a1849654204f0876
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="csimplemap-class"></a>CSimpleMap 클래스
이 클래스는 단순한 매핑 배열에 대 한 지원을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>  
class CSimpleMap
```  
  
#### <a name="parameters"></a>매개 변수  
 `TKey`  
 중요 한 요소 형식입니다.  
  
 `TVal`  
 값 요소 형식입니다.  
  
 `TEqual`  
 형식의 요소에 대 한 같음 테스트를 정의 하는 특성 개체를 `T`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|값 형식에 대 한 Typedef입니다.|  
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|키 형식에 대 한 Typedef입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleMap::CSimpleMap](#csimplemap)|생성자입니다.|  
|[CSimpleMap:: ~ CSimpleMap](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleMap::Add](#add)|맵 배열에 키와 연결 된 값을 추가합니다.|  
|[CSimpleMap::FindKey](#findkey)|특정 키를 찾습니다.|  
|[CSimpleMap::FindVal](#findval)|특정 값을 찾습니다.|  
|[CSimpleMap::GetKeyAt](#getkeyat)|지정된 된 키를 검색합니다.|  
|[CSimpleMap::GetSize](#getsize)|매핑 배열의 항목 수를 반환합니다.|  
|[CSimpleMap::GetValueAt](#getvalueat)|지정된 된 값을 검색합니다.|  
|[CSimpleMap::Lookup](#lookup)|지정된 된 키와 연결 된 값을 반환 합니다.|  
|[CSimpleMap::Remove](#remove)|키와 일치 하는 값을 제거 합니다.|  
|[CSimpleMap::RemoveAll](#removeall)|모든 키와 값을 제거합니다.|  
|[CSimpleMap::RemoveAt](#removeat)|특정 키와 일치 하는 값을 제거합니다.|  
|[CSimpleMap::ReverseLookup](#reverselookup)|지정 된 값과 연결 된 키를 반환 합니다.|  
|[CSimpleMap::SetAt](#setat)|지정된 된 키와 연결 된 값을 설정 합니다.|  
|[CSimpleMap::SetAtIndex](#setatindex)|특정 키와 값을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 `CSimpleMap`지정 된 형식의 단순 매핑 배열에 대 한 지원을 제공 `T`, 주요 요소와 연결 된 값의 순서가 지정 되지 않은 배열을 관리 합니다.  
  
 매개 변수 `TEqual` 형식의 두 가지 요소에 대 한 같음 함수를 정의 하는 방법을 제공 `T`합니다. 클래스를 만들어 비슷합니다 [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), 모든 지정 된 배열에 대 한 같음 테스트의 동작을 변경 하는 것이 불가능 합니다. 예를 들어 포인터의 배열로 처리할 때에 포인터를 참조할 값에 따라 일치로 정의 유용할 수 있습니다. 기본 구현은 활용 **operator==()**합니다.  
  
 둘 다 `CSimpleMap` 및 [CSimpleArray](../../atl/reference/csimplearray-class.md) 이전 ATL와의 호환성을 해제 하 고 완전 하 고 효율적인 컬렉션 구현은에서 제공 됩니다에 대 한 제공 [CAtlArray](../../atl/reference/catlarray-class.md) 및 [ CAtlMap](../../atl/reference/catlmap-class.md)합니다.  
  
 ATL 및 MFC에서 다른 맵 컬렉션와 달리 단순 배열을 사용 하 여이 클래스가 구현 되는 및 lookup 검색 선형 검색을 요구 합니다. `CAtlMap`배열 많은 수의 요소를 포함 하는 경우 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpcoll.h  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleMap::Add  
 맵 배열에 키와 연결 된 값을 추가합니다.  
  
```
BOOL Add(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 키입니다.  
  
 *val*  
 연결 된 값입니다.  
  
### <a name="return-value"></a>반환 값  
 키와 값 했는데이 성공적으로 추가 된이 고, FALSE 그렇지 않으면 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 각 키 / 값 쌍의 매핑을 해제 하 고 다시 할당 하려면, 각각에 대 한 데이터는 항상 연속적으로 저장을 보장 하기 위해 메모리 배열 원인을 추가 합니다. 즉, 두 번째 키 요소 항상 바로 뒤에 오는 첫 번째 키 요소를 메모리에 등입니다.  
  
##  <a name="_arrayelementtype"></a>CSimpleMap::_ArrayElementType  
 키 형식에 대 한 typedef입니다.  
  
```
typedef TVal _ArrayElementType;
```  
  
##  <a name="_arraykeytype"></a>CSimpleMap::_ArrayKeyType  
 값 형식에 대 한 typedef입니다.  
  
```
typedef TKey _ArrayKeyType;
```  
  
##  <a name="csimplemap"></a>CSimpleMap::CSimpleMap  
 생성자입니다.  
  
```
CSimpleMap();
```  
  
### <a name="remarks"></a>설명  
 데이터 멤버를 초기화합니다.  
  
##  <a name="dtor"></a>CSimpleMap:: ~ CSimpleMap  
 소멸자입니다.  
  
```
~CSimpleMap();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="findkey"></a>CSimpleMap::FindKey  
 특정 키를 찾습니다.  
  
```
int FindKey(const TKey& key) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 검색할 키입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않은 경우는 키의 인덱스를 찾을 수를 반환-1을 반환 합니다.  
  
##  <a name="findval"></a>CSimpleMap::FindVal  
 특정 값을 찾습니다.  
  
```
int FindVal(const TVal& val) const;
```  
  
### <a name="parameters"></a>매개 변수  
 *val*  
 검색할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값의 인덱스를 찾으면 그렇지 않으면-1을 반환 합니다.  
  
##  <a name="getkeyat"></a>CSimpleMap::GetKeyAt  
 지정된 된 인덱스에 키를 검색합니다.  
  
```
TKey& GetKeyAt(int nIndex) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 반환할 키의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 키에서 참조를 반환 `nIndex`합니다.  
  
### <a name="remarks"></a>설명  
 로 전달 하는 인덱스 `nIndex` 의미 있는 반환 값에 대해 유효 해야 합니다.  
  
##  <a name="getsize"></a>CSimpleMap::GetSize  
 매핑 배열의 항목 수를 반환합니다.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>반환 값  
 매핑 배열에 있는 항목 (키와 값은 하나의 항목)의 수를 반환 합니다.  
  
##  <a name="getvalueat"></a>CSimpleMap::GetValueAt  
 특정 인덱스에 있는 값을 검색합니다.  
  
```
TVal& GetValueAt(int nIndex) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 반환할 값의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 참조 하는 값을 반환 `nIndex`합니다.  
  
### <a name="remarks"></a>설명  
 로 전달 하는 인덱스 `nIndex` 의미 있는 반환 값에 대해 유효 해야 합니다.  
  
##  <a name="lookup"></a>CSimpleMap::Lookup  
 지정된 된 키와 연결 된 값을 반환 합니다.  
  
```
TVal Lookup(const TKey& key) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 키입니다.  
  
### <a name="return-value"></a>반환 값  
 연결 된 값을 반환합니다. Null 일치 하는 키가 없으면 반환 됩니다.  
  
##  <a name="remove"></a>CSimpleMap::Remove  
 키와 일치 하는 값을 제거 합니다.  
  
```
BOOL Remove(const TKey& key);
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 키입니다.  
  
### <a name="return-value"></a>반환 값  
 키 및 일치 하는 값 했는데이 성공적으로 제거, FALSE 그렇지 않으면 TRUE를 반환 합니다.  
  
##  <a name="removeall"></a>CSimpleMap::RemoveAll  
 모든 키와 값을 제거합니다.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>설명  
 매핑 배열 개체에서 모든 키와 값을 제거합니다.  
  
##  <a name="removeat"></a>CSimpleMap::RemoveAt  
 키와 지정된 된 인덱스에 연결 된 값을 제거 합니다.  
  
```
BOOL RemoveAt(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 키와 키를 제거 하려면 연결 된 값의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE를 반환 성공, FALSE에 지정 된 인덱스에 잘못 된 인덱스인 경우.  
  
##  <a name="reverselookup"></a>CSimpleMap::ReverseLookup  
 지정 된 값과 연결 된 키를 반환 합니다.  
  
```
TKey ReverseLookup(const TVal& val) const;
```  
  
### <a name="parameters"></a>매개 변수  
 *val*  
 값입니다.  
  
### <a name="return-value"></a>반환 값  
 연결 된 키를 반환합니다. Null 일치 하는 키가 없으면 반환 됩니다.  
  
##  <a name="setat"></a>CSimpleMap::SetAt  
 지정된 된 키와 연결 된 값을 설정 합니다.  
  
```
BOOL SetAt(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 키입니다.  
  
 *val*  
 할당할 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 값이 성공적으로 변경 된이 고, FALSE를 키 발견 하는 경우 TRUE를 반환 합니다.  
  
##  <a name="setatindex"></a>CSimpleMap::SetAtIndex  
 지정된 된 인덱스에 키와 값을 설정합니다.  
  
```
BOOL SetAtIndex(  
    int nIndex,
    const TKey& key,
    const TVal& val);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 키와 값을 변경 하려면 쌍으로 연결을 참조 하는 인덱스입니다.  
  
 `key`  
 새 키입니다.  
  
 *val*  
 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 경우 TRUE를 반환 성공이 고, FALSE 인덱스가 잘못 되었습니다.  
  
### <a name="remarks"></a>설명  
 키와 값을 가리키는 업데이트 `nIndex`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
