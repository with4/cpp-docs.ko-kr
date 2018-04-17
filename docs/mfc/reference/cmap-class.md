---
title: CMap 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
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
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd7c1b23e3c586bf89a86e17d85ee5b5050fbf37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmap-class"></a>CMap 클래스
고유 키를 값에 매핑하는 사전 컬렉션 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>매개 변수  
 `KEY`  
 맵에 대 한 키로 사용 되는 개체의 클래스입니다.  
  
 `ARG` *_* `KEY`  
 데이터 형식에 사용 되는 `KEY` 인수에 대 한 참조, 일반적으로 `KEY`합니다.  
  
 `VALUE`  
 Map에 저장 된 개체의 클래스입니다.  
  
 `ARG` *_* `VALUE`  
 데이터 형식에 사용 되는 `VALUE` 인수에 대 한 참조, 일반적으로 `VALUE`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-structures"></a>공용 구조체  
  
|이름|설명|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|키 값과 연결된 된 개체의 값을 포함 하는 중첩 된 구조입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|키 값에 매핑되는 컬렉션을 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|이 맵에서 요소의 수를 반환합니다.|  
|[CMap::GetHashTableSize](#gethashtablesize)|해시 테이블의 요소 수를 반환합니다.|  
|[CMap::GetNextAssoc](#getnextassoc)|반복 하는 데 다음 요소를 가져옵니다.|  
|[CMap::GetSize](#getsize)|이 맵에서 요소의 수를 반환합니다.|  
|[CMap::GetStartPosition](#getstartposition)|첫 번째 요소의 위치를 반환합니다.|  
|[CMap::InitHashTable](#inithashtable)|해시 테이블을 초기화 하 고 크기를 지정 합니다.|  
|[CMap::IsEmpty](#isempty)|빈 맵 조건 (요소 없음)에 대해 테스트 합니다.|  
|[CMap::Lookup](#lookup)|지정된 된 키에 매핑된 값을 찾습니다.|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|첫 번째 요소에 대 한 포인터를 반환합니다.|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|반복 하는 데 다음 요소에 대 한 포인터를 가져옵니다.|  
|[CMap::PLookup](#plookup)|지정된 된 값을 일치 하는 값을 갖는 키에 대 한 포인터를 반환 합니다.|  
|[CMap::RemoveAll](#removeall)|이 맵에서 모든 요소를 제거합니다.|  
|[CMap::RemoveKey](#removekey)|키가 지정 하는 요소를 제거 합니다.|  
|[CMap::SetAt](#setat)|map에 요소를 삽입 일치 하는 키가 있을 경우 기존 요소를 바꿉니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CMap::operator]](#operator_at)|지도 요소를 삽입-한 연산자의 대체 `SetAt`합니다.|  
  
## <a name="remarks"></a>설명  
 지도에 키-값 쌍 (요소)를 삽입 하면 효율적으로 검색 하거나 액세스 키를 사용 하는 쌍을 삭제할 수 있습니다. Map의 모든 요소를 반복할 수도 있습니다.  
  
 형식의 변수 **위치** 항목에 대 한 대체 액세스에 사용 됩니다. 사용할 수는 **위치** 항목 "기억" 하 고 맵을 통해 반복 하 합니다. 이 반복은 키 값으로 순차적 이라고 생각할 수도 있습니다. 그것이 아니야. 검색 된 요소의 순서는 결정 되지 않습니다.  
  
 글로벌 도우미 함수를이 클래스 호출의 특정 멤버 함수는 대부분 용도에 대 한 사용자 지정 되어야 합니다는 `CMap` 클래스입니다. 참조 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) 의 매크로 및 전역 섹션에는 `MFC Reference`합니다.  
  
 `CMap`재정의 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) serialization 및 요소 덤프를 지원 하도록 합니다. 맵을 사용 하 여 보관 파일에 저장 되는 경우 `Serialize`, 각 지도 요소 차례로 serialize 됩니다. 기본 구현에서 `SerializeElements` 도우미 함수는 비트 쓰기를 수행 합니다. 파생 된 포인터 컬렉션 항목의 직렬화에 대 한 내용은 `CObject` 다른 사용자 정의 형식을 참조 또는 [하는 방법: 형식이 안전한 컬렉션 만들기](../../mfc/how-to-make-a-type-safe-collection.md)합니다.  
  
 (키 및 값) 맵에서 개별 요소의 진단 덤프 해야 할 경우 덤프 컨텍스트 깊이 1 이상으로 설정 해야 합니다.  
  
 경우는 `CMap` 개체를 삭제 하거나 해당 요소를 제거할 키와 값 모두 제거 됩니다.  
  
 맵 클래스를 파생 목록 파생 하는 것과 비슷합니다. 문서 참조 [컬렉션](../../mfc/collections.md) 특수 한 용도의 목록 클래스의 파생에 대 한 예제입니다.  
  
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
 지도 확장 하기 위한 메모리 할당 세분성을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 단위에서 메모리를 할당 지도 확장 되면서 `nBlockSize` 항목입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="cpair"></a>CMap::CPair  
 키 값과 연결된 된 개체의 값을 포함합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스 내에서 중첩된 구조 [CMap](../../mfc/reference/cmap-class.md)합니다.  
  
 구조는 두 가지 필드로 구성 됩니다.  
  
- **키** 키 형식의 실제 값입니다.  
  
- **값** 연결된 된 개체의 값입니다.  
  
 반환 값을 저장 하는 데 사용 됩니다 [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), 및 [CMap::PGetNextAssoc](#pgetnextassoc)합니다.  
  
### <a name="example"></a>예  
 사용의 예에 대 한 예제를 참조 하십시오. [CMap::PLookup](#plookup)합니다.  
  
##  <a name="getcount"></a>CMap::GetCount  
 Map의 요소 수를 검색 합니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 요소의 수입니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMap::Lookup](#lookup)합니다.  
  
##  <a name="gethashtablesize"></a>CMap::GetHashTableSize  
 지도 대 한 해시 테이블에 있는 요소의 수를 결정합니다.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 해시 테이블에 있는 요소의 수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
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
  
 *KEY*  
 Map의 키 유형을 지정 하는 템플릿 매개 변수  
  
 `rKey`  
 검색 된 요소의 반환 된 키를 지정합니다.  
  
 *값*  
 Map의 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `rValue`  
 검색 된 요소의 반환 된 값을 지정합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 map의 모든 요소를 통해 반복 하는 데 가장 유용 합니다. 참고 위치 시퀀스 아닌지 반드시 키 값 시퀀스와 동일 합니다.  
  
 검색된 된 요소는 맵에서 마지막 다음 새 값의 경우 `rNextPosition` 로 설정 된 **NULL**합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMap::SetAt](#setat)합니다.  
  
##  <a name="getsize"></a>CMap::GetSize  
 지도 요소 수를 반환합니다.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 지도 있는 항목의 수입니다.  
  
### <a name="remarks"></a>설명  
 Map의 요소 수를 검색 하려면이 메서드를 호출 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CMap::GetStartPosition  
 가 반환 하 여 맵 반복을 시작할는 **위치** 에 전달 될 수 있는 값을 `GetNextAssoc` 호출 합니다.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 지도; 반복 하기 위한 시작 위치를 나타내는 값 또는 **NULL** 맵이 비어 있는 경우.  
  
### <a name="remarks"></a>설명  
 반복 순서는 예측할 수 없으며; 따라서 "맵 내에서 요소 첫 번째" 특별 한 의미가 없습니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMap::SetAt](#setat)합니다.  
  
##  <a name="inithashtable"></a>CMap::InitHashTable  
 해시 테이블을 초기화합니다.  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);  
```  
  
### <a name="parameters"></a>매개 변수  
 `hashSize`  
 해시 테이블에 있는 항목의 수입니다.  
  
 `bAllocNow`  
 경우 **TRUE**, 초기화; 시 해시 테이블을 할당 필요할 때 테이블 할당 되는 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 최상의 성능을 얻으려면 해시 테이블 크기 소수 이어야 합니다. 충돌을 최소화 하려면 크기 해야 약 20%는 가장 큰 예상된 데이터 집합 보다 큰 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMap::Lookup](#lookup)합니다.  
  
##  <a name="isempty"></a>CMap::IsEmpty  
 지도 비어 있는지 여부를 결정 합니다.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 지도 요소가 포함 되어 있지 않으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMap::RemoveAll](#removeall)합니다.  
  
##  <a name="lookup"></a>CMap::Lookup  
 지정된 된 키에 매핑된 값을 찾습니다.  
  
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
 요소가 발견 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `Lookup`정확 하 게 지정된 된 키와 일치 하는 키가 있는 지도 요소를 빠르게 찾기 위해 해싱 알고리즘을 사용 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="operator_at"></a>CMap::operator]  
 에 대 한 편리한 대체는 `SetAt` 멤버 함수입니다.  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>매개 변수  
 *값*  
 지도 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `ARG_KEY`  
 템플릿 매개 변수는 키 값의 형식을 지정 합니다.  
  
 `key`  
 지도에서 값을 검색 하는 데 사용 하는 키입니다.  
  
### <a name="remarks"></a>설명  
 따라서 대입문 (l-value)의 왼쪽에만 사용할 수 있습니다. 지정된 된 키와 지도 요소가 경우 새 요소는 생성 됩니다.  
  
 없습니다 "오른쪽" (r-value)이이 운영자에 게 해당 되므로은 실패할 가능성이 있는 지도에서 키를 찾을 수 있습니다. 사용 하 여 `Lookup` 요소 검색에 대 한 멤버 함수입니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMap::Lookup](#lookup)합니다.  
  
##  <a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 Map 개체의 첫 번째 항목을 반환합니다.  
  
```  
const CPair* PGetFirstAssoc() const; 
CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>반환 값  
 맵에서; 첫 번째 항목에 대 한 포인터 참조 [CMap::CPair](#cpair)합니다. 지도 항목이 없는 경우이 값은 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 Map 개체에 대 한 포인터는 첫 번째 요소를 반환 하려면이 함수를 호출 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 가 가리키는 지도 요소를 검색 `pAssocRec`합니다.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAssocRet*  
 이전에서 반환 된 맵 항목을 가리키는 [PGetNextAssoc](#pgetnextassoc) 또는 [CMap::PGetFirstAssoc](#pgetfirstassoc) 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 지도;에서 다음 항목에 대 한 포인터 참조 [CMap::CPair](#cpair)합니다. 값은 해당 요소가 맵의 마지막 이면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 Map의 모든 요소를 반복 하는이 메서드를 호출 합니다. 첫 번째 요소를 호출 하 여 검색 `PGetFirstAssoc` 는 지도에 대 한 연속 호출은을 반복 하 고 `PGetNextAssoc`합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMap::PGetFirstAssoc](#pgetfirstassoc)합니다.  
  
##  <a name="plookup"></a>CMap::PLookup  
 지정된 된 키에 매핑된 값을 찾습니다.  
  
```  
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 검색할 요소의 키입니다.  
  
### <a name="return-value"></a>반환 값  
 키 구조;에 대 한 포인터 참조 [CMap::CPair](#cpair)합니다. 일치 없을 경우 `CMap::PLookup` 반환 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 키를 정확 하 게 일치 하는 키를 사용 하 여 지도 요소에 대 한 검색 하려면이 메서드를 호출 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>CMap::RemoveAll  
 전역 도우미 함수를 호출 하 여 모든 값이 맵에서 제거 **DestructElements**합니다.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>설명  
 함수는 맵이 비어 이미 경우 제대로 작동 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>CMap::RemoveKey  
 제공 된 키;에 해당 하는 맵 항목을 조회 그런 다음 키가 있으면 항목을 제거 합니다.  
  
```  
BOOL RemoveKey(ARG_KEY key);
```  
  
### <a name="parameters"></a>매개 변수  
 `ARG_KEY`  
 키의 형식을 지정 하는 템플릿 매개 변수  
  
 `key`  
 제거할 요소의 키입니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 찾아 제거 되었으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 **DestructElements** 도우미 함수를 사용 하는 항목을 제거 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMap::SetAt](#setat)합니다.  
  
##  <a name="setat"></a>CMap::SetAt  
 기본 지도에 요소를 삽입 하려면 의미 합니다.  
  
```  
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `ARG_KEY`  
 템플릿 매개 변수 유형을 지정 하는 `key` 매개 변수입니다.  
  
 `key`  
 새 요소의 키를 지정합니다.  
  
 `ARG_VALUE`  
 템플릿 매개 변수 유형을 지정 하는 `newValue` 매개 변수입니다.  
  
 `newValue`  
 새 요소의 값을 지정합니다.  
  
### <a name="remarks"></a>설명  
 첫째, 키가 찾습니다. 키가 있으면 해당 값이 변경 됩니다; 그런 다음 그렇지 않으면 새 키-값 쌍이 생성 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)  
