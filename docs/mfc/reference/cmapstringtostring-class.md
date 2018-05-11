---
title: CMapStringToString 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMapStringToString [MFC], CPair
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a196e2f3f4641d94bbbbda57dd1471066fb1dfa2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cmapstringtostring-class"></a>CMapStringToString 클래스
`CString` 개체로 키가 지정된 `CString` 개체의 맵을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMapStringToString : public CObject  
```  
  
## <a name="members"></a>멤버  
 멤버 함수 `CMapStringToString` 클래스의 멤버 함수와 비슷한 [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)합니다. 이처럼 두 함수가 비슷하므로 `CMapStringToOb` 참조 설명서에서 멤버 함수 관련 사항을 확인할 수 있습니다. 볼 때마다는 `CObject` 포인터를 반환 값 또는 "출력" 작동 매개 변수를 대체에 대 한 포인터 `char`합니다. 볼 때마다는 `CObject` "입력된" 함수 매개 변수로 사용 하는 포인터에 대 한 포인터를 대체 `char`합니다.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 예를 들어 위의 코드는  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### <a name="public-structures"></a>공용 구조체  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToString::CPair](#cpair)|키 값과 연결 된 문자열 개체의 값을 포함 하는 중첩 된 구조입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|이 맵에서 요소의 수를 반환합니다.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|현재 해시 테이블의 요소 수를 결정합니다.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|반복 하는 데 다음 요소를 가져옵니다.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|이 맵에서 요소의 수를 반환합니다.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|첫 번째 요소의 위치를 반환합니다.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|지정된 된 키의 해시 값을 계산합니다.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|해시 테이블을 초기화합니다.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|빈 맵 조건 (요소 없음)에 대해 테스트 합니다.|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void 포인터는 void 포인터 키에 기반을 찾습니다. 이것이 가리키는 엔터티 하지 포인터 값을 키 비교에 사용 됩니다.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|지정 된 키 값과 연결 된 키에 대 한 참조를 반환 합니다.|  
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|첫 번째에 대 한 포인터를 가져옵니다 `CString` 맵에서 합니다.|  
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|다음에 대 한 포인터를 가져옵니다 `CString` 반복 하는 데 있습니다.|  
|[CMapStringToString::PLookup](#plookup)|에 대 한 포인터를 반환 합니다.는 `CString` 값을 갖는 지정 된 값과 일치 합니다.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|이 맵에서 모든 요소를 제거합니다.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|키가 지정 하는 요소를 제거 합니다.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|map에 요소를 삽입 일치 하는 키가 있을 경우 기존 요소를 바꿉니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::operator [ ]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|지도 요소를 삽입-한 연산자의 대체 `SetAt`합니다.|  
  
## <a name="remarks"></a>설명  
 `CMapStringToString`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다. 지도 오버 로드 된 삽입을 사용 하 여 보관 저장소에 저장 되는 경우 각 요소가 차례로 serialize 됩니다 ( **<<**) 연산자 또는 `Serialize` 멤버 함수입니다.  
  
 개인의 덤프 해야 할 경우 `CString` -  `CString` 요소를 1 이상으로 덤프 컨텍스트 깊이 설정 해야 합니다.  
  
 경우는 `CMapStringToString` 개체를 삭제 하거나 해당 요소를 제거 하는 경우는 `CString` 개체를 적절 하 게 제거 됩니다.  
  
 대 한 자세한 내용은 `CMapStringToString`, 문서를 참조 [컬렉션](../../mfc/collections.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcoll.h  
  
##  <a name="cpair"></a>  CMapStringToString::CPair  
 키 값과 연결 된 문자열 개체의 값을 포함합니다.  
  
### <a name="remarks"></a>설명  
 이 클래스 내에서 중첩된 구조 [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)합니다.  
  
 구조는 두 가지 필드로 구성 됩니다.  
  
- **키** 키 형식의 실제 값입니다.  
  
- **값** 연결된 된 개체의 값입니다.  
  
 반환 값을 저장 하는 데 사용 됩니다 [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), 및 [CMapStringToString::PGetNextAssoc](#pgetnextassoc)합니다.  
  
### <a name="example"></a>예제  
  사용의 예에 대 한 예제를 참조 하십시오. [CMapStringToString::PLookup](#plookup)합니다.  
  
##  <a name="pgetfirstassoc"></a>  CMapStringToString::PGetFirstAssoc  
 Map 개체의 첫 번째 항목을 반환합니다.  
  
```  
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```  
  
### <a name="return-value"></a>반환 값  
 맵에서; 첫 번째 항목에 대 한 포인터 참조 [CMapStringToString::CPair](#cpair)합니다. 값은 지도 비어 있으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 Map 개체에 대 한 포인터는 첫 번째 요소를 반환 하려면이 함수를 호출 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]  
  
##  <a name="pgetnextassoc"></a>  CMapStringToString::PGetNextAssoc  
 가 가리키는 지도 요소를 검색 `pAssocRec`합니다.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssoc) const;  
  
CPair *PGetNextAssoc(const CPair* pAssoc);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAssoc*  
 이전에서 반환 된 맵 항목을 가리키는 [PGetNextAssoc](#pgetnextassoc) 또는 [PGetFirstAssoc](#pgetfirstassoc) 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 지도;에서 다음 항목에 대 한 포인터 참조 [CMapStringToString::CPair](#cpair)합니다. 값은 해당 요소가 맵의 마지막 이면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 Map의 모든 요소를 반복 하는이 메서드를 호출 합니다. 첫 번째 요소를 호출 하 여 검색 `PGetFirstAssoc` 는 지도에 대 한 연속 호출은을 반복 하 고 `PGetNextAssoc`합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)합니다.  
  
##  <a name="plookup"></a>  CMapStringToString::PLookup  
 지정된 된 키에 매핑된 값을 찾습니다.  
  
```  
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 검색 한 요소에 대 한 키에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 키에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 키를 정확 하 게 일치 하는 키를 사용 하 여 지도 요소에 대 한 검색 하려면이 메서드를 호출 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



