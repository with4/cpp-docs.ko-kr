---
title: "CMapStringToOb 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
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
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs: C++
helpviewer_keywords:
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
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a840677819710247e73aa8e3bcb904be756f852
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb 클래스
고유한 `CString` 개체를 `CObject` 포인터에 매핑하는 사전 컬렉션 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMapStringToOb : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](#getcount)|이 맵에서 요소의 수를 반환합니다.|  
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|현재 해시 테이블의 요소 수를 결정합니다.|  
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|반복 하는 데 다음 요소를 가져옵니다.|  
|[CMapStringToOb::GetSize](#getsize)|이 맵에서 요소의 수를 반환합니다.|  
|[CMapStringToOb::GetStartPosition](#getstartposition)|첫 번째 요소의 위치를 반환합니다.|  
|[CMapStringToOb::HashKey](#hashkey)|지정된 된 키의 해시 값을 계산합니다.|  
|[CMapStringToOb::InitHashTable](#inithashtable)|해시 테이블을 초기화합니다.|  
|[CMapStringToOb::IsEmpty](#isempty)|빈 맵 조건 (요소 없음)에 대해 테스트 합니다.|  
|[CMapStringToOb::Lookup](#lookup)|Void 포인터는 void 포인터 키에 기반을 찾습니다. 이것이 가리키는 엔터티 하지 포인터 값을 키 비교에 사용 됩니다.|  
|[CMapStringToOb::LookupKey](#lookupkey)|지정 된 키 값과 연결 된 키에 대 한 참조를 반환 합니다.|  
|[CMapStringToOb::RemoveAll](#removeall)|이 맵에서 모든 요소를 제거합니다.|  
|[CMapStringToOb::RemoveKey](#removekey)|키가 지정 하는 요소를 제거 합니다.|  
|[CMapStringToOb::SetAt](#setat)|map에 요소를 삽입 일치 하는 키가 있을 경우 기존 요소를 바꿉니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::operator]](#operator_at)|지도 요소를 삽입-한 연산자의 대체 `SetAt`합니다.|  
  
## <a name="remarks"></a>설명  
 삽입 한 후 한 `CString` -  `CObject*` 쌍 (요소)를 map으로 효율적으로 검색 하거나 삭제할 수는 문자열을 사용 하 여 쌍 또는 `CString` 값이 키로 합니다. Map의 모든 요소를 반복할 수도 있습니다.  
  
 형식의 변수 **위치** 모든 지도 변형에 대 한 대체 항목 액세스에 사용 됩니다. 사용할 수는 **위치** 항목 "기억" 하 고 맵을 통해 반복 하 합니다. 이 반복은 키 값으로 순차적 이라고 생각할 수도 있습니다. 그것이 아니야. 검색 된 요소의 순서는 결정 되지 않습니다.  
  
 `CMapStringToOb`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다. 지도 오버 로드 된 삽입을 사용 하 여 보관 저장소에 저장 되는 경우 각 요소가 차례로 serialize 됩니다 (  **<<** ) 연산자 또는 `Serialize` 멤버 함수입니다.  
  
 지도에 있는 개별 요소의 진단 덤프 해야 하는 경우 (의 `CString` 값 및 `CObject` 내용을), 덤프 컨텍스트 깊이 1 이상으로 설정 해야 합니다.  
  
 경우는 `CMapStringToOb` 개체를 삭제 하거나 해당 요소를 제거 하는 경우는 `CString` 개체 및 `CObject` 포인터 제거 됩니다. 참조 하는 개체는 `CObject` 포인터 소멸 되지 않습니다.  
  
 맵 클래스를 파생 목록 파생 하는 것과 비슷합니다. 문서 참조 [컬렉션](../../mfc/collections.md) 특수 한 용도의 목록 클래스의 파생에 대 한 예제입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcoll.h  
  
##  <a name="cmapstringtoob"></a>CMapStringToOb::CMapStringToOb  
 빈 생성 `CString`을 아래와 같이 `CObject*` 맵.  
  
```  
CMapStringToOb(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 지도 확장 하기 위한 메모리 할당 세분성을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 단위에서 메모리를 할당 지도 확장 되면서 `nBlockSize` 항목입니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 **CMapStringToOb:: CMapStringToOb**합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]  
  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
##  <a name="getcount"></a>CMapStringToOb::GetCount  
 지도에 있는 요소의 수를 결정 합니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 맵에서 요소의 수입니다.  
  
### <a name="remarks"></a>설명  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::GetCount`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]  
  
##  <a name="gethashtablesize"></a>CMapStringToOb::GetHashTableSize  
 현재 해시 테이블의 요소 수를 결정합니다.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 해시 테이블의 요소 수를 반환합니다.  
  
### <a name="remarks"></a>설명  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::GetHashTableSize`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; UINT GetHashTableSize)**|  
  
##  <a name="getnextassoc"></a>CMapStringToOb::GetNextAssoc  
 에 지도 요소를 검색 *rNextPosition*, 그런 다음 업데이트 *rNextPosition* 맵에서 다음 요소를 참조 하 합니다.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,  
    CString& rKey,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *rNextPosition*  
 에 대 한 참조를 지정 된 **위치** 이전에서 반환 된 값 **GetNextAssoc** 또는 **GetStartPosition** 호출 합니다.  
  
 *rKey*  
 검색된 된 요소 (문자열)의 반환 된 키를 지정합니다.  
  
 *rValue*  
 검색 된 요소의 반환 된 값을 지정 합니다 (한 **CObject** 포인터). 이 매개 변수에 대 한 자세한 정보에 대 한 설명을 참조 하세요.  
  
### <a name="remarks"></a>설명  
 이 함수는 map의 모든 요소를 통해 반복 하는 데 가장 유용 합니다. 참고 위치 시퀀스 아닌지 반드시 키 값 시퀀스와 동일 합니다.  
  
 검색된 된 요소는 맵에서 마지막 다음 새 값의 경우 *rNextPosition* 로 설정 된 **NULL**합니다.  
  
 에 대 한는 *rValue* 매개 변수를 개체 유형 캐스팅 해야 **CObject\*&**, 않는 컴파일러의 필요, 다음 예제와 같이:  
  
 [!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]  
  
 이 여기에 해당 **GetNextAssoc** 템플릿을 기반으로 하는 지도 대 한 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 **CMapStringToOb::GetNextAssoc**합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, void\* &**  *rKey* **, void\* &**  *rValue* **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, void\* &**  *rKey* **, WORD 및** *rValue* **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, CString &** *rKey* **, void\* &**  *rValue* **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, CString &** *rKey* **, CString &** *rValue* **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, WORD &** *rKey* **, CObject\* &**  *rValue* **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**GetNextAssoc void (위치 &** *rNextPosition* **, WORD &** *rKey* **, void\* &**  *rValue* **) const;**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `Lisa : a CAge at $4724 11`  
  
 `Marge : a CAge at $47A8 35`  
  
 `Homer : a CAge at $4766 36`  
  
 `Bart : a CAge at $45D4 13`  
  
##  <a name="getsize"></a>CMapStringToOb::GetSize  
 지도 요소 수를 반환합니다.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 지도 있는 항목의 수입니다.  
  
### <a name="remarks"></a>설명  
 Map의 요소 수를 검색 하려면이 메서드를 호출 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::GetSize`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]  
  
##  <a name="getstartposition"></a>CMapStringToOb::GetStartPosition  
 가 반환 하 여 맵 반복을 시작할는 **위치** 에 전달 될 수 있는 값을 `GetNextAssoc` 호출 합니다.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 지도; 반복 하기 위한 시작 위치를 나타내는 값 또는 **NULL** 맵이 비어 있는 경우.  
  
### <a name="remarks"></a>설명  
 반복 순서는 예측할 수 없으며; 따라서 "맵 내에서 요소 첫 번째" 특별 한 의미가 없습니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::GetStartPosition`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; GetStartPosition ()를 배치 합니다.**|  
  
### <a name="example"></a>예  
 예를 참조 [CMapStringToOb::GetNextAssoc](#getnextassoc)합니다.  
  
##  <a name="hashkey"></a>CMapStringToOb::HashKey  
 지정된 된 키의 해시 값을 계산합니다.  
  
```  
UINT HashKey(LPCTSTR key) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 해시 값을 계산 하는 키입니다.  
  
### <a name="return-value"></a>반환 값  
 키의 해시 값  
  
### <a name="remarks"></a>설명  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::HashKey`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void\***  `key` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void\***  `key` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (WORD** `key` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (WORD** `key` **) const;**|  
  
##  <a name="inithashtable"></a>CMapStringToOb::InitHashTable  
 해시 테이블을 초기화합니다.  
  
```  
void InitHashTable(
    UINT hashSize,  
    BOOL bAllocNow = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `hashSize`  
 해시 테이블에 있는 항목의 수입니다.  
  
 `bAllocNow`  
 경우 **TRUE**, 초기화; 시 해시 테이블을 할당 필요할 때 테이블 할당 되는 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 최상의 성능을 얻으려면 해시 테이블 크기 소수 이어야 합니다. 충돌을 최소화 하려면 크기 해야 약 20%는 가장 큰 예상된 데이터 집합 보다 큰 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::InitHashTable`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**InitHashTable void (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**InitHashTable void (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**InitHashTable void (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**InitHashTable void (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**InitHashTable void (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**InitHashTable void (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
  
##  <a name="isempty"></a>CMapStringToOb::IsEmpty  
 지도 비어 있는지 여부를 결정 합니다.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 지도 요소가 포함 되어 있지 않으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 예를 참조 [RemoveAll](#removeall)합니다.  
  
### <a name="remarks"></a>설명  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 **CMapStringToOb:: IsEmpty**합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**IsEmpty () const; BOOL**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**IsEmpty () const; BOOL**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**IsEmpty () const; BOOL**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**IsEmpty () const; BOOL**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**IsEmpty () const; BOOL**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**IsEmpty () const; BOOL**|  
  
##  <a name="lookup"></a>CMapStringToOb::Lookup  
 반환 된 `CObject` 기반 포인터는 `CString` 값입니다.  
  
```  
BOOL Lookup(
    LPCTSTR key,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 조회 되는 요소를 식별 하는 문자열 키를 지정 합니다.  
  
 `rValue`  
 조회 요소에서 반환 된 값을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 발견 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `Lookup`해시 알고리즘을 사용 하 여 신속 하 게 정확히 일치 하는 키가 있는 지도 요소를 찾습니다 ( `CString` 값).  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::LookUp`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL 조회 (void\***  `key` **, void\* &**  `rValue` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL 조회 (void\***  `key` **, WORD &** `rValue` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL 조회 (LPCTSTR** `key` **, void\* &**  `rValue` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL 조회 (LPCTSTR** `key` **, CString &** `rValue` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL 조회 (WORD** `key` **, CObject\* &**  `rValue` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL 조회 (WORD** `key` **, void\* &**  `rValue` **) const;**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]  
  
##  <a name="lookupkey"></a>CMapStringToOb::LookupKey  
 지정 된 키 값과 연결 된 키에 대 한 참조를 반환 합니다.  
  
```  
BOOL LookupKey(
    LPCTSTR key,  
    LPCTSTR& rKey) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 조회 되는 요소를 식별 하는 문자열 키를 지정 합니다.  
  
 `rKey`  
 연결 된 키에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 키가 있으면; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 키에 대 한 참조를 사용 하 여 맵에서 관련된 요소가 제거 된 후 사용 하는 경우 또는 지도 소멸 된 후에 안전 하지 않습니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 **CMapStringToOb:: LookupKey**합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
  
##  <a name="operator_at"></a>CMapStringToOb::operator]  
 에 대 한 편리한 대체는 `SetAt` 멤버 함수입니다.  
  
```  
CObject*& operator[ ](lpctstr key);
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터에 대 한 참조는 `CObject` ; 개체 또는 **NULL** 맵이 비어 있는 경우 또는 `key` 범위를 벗어났습니다.  
  
### <a name="remarks"></a>설명  
 따라서 대입문 (l-value)의 왼쪽에만 사용할 수 있습니다. 지정된 된 키와 지도 요소가 경우 새 요소는 생성 됩니다.  
  
 없습니다 "오른쪽" (r-value)이이 운영자에 게 해당 되므로은 실패할 가능성이 있는 지도에서 키를 찾을 수 있습니다. 사용 하 여 `Lookup` 요소 검색에 대 한 멤버 함수입니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 **CMapStringToOb::operator**합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void\*& 연산자 (void\***  `key`  **\);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD & 연산자 (void\***  `key`  **\);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& 연산자 (lpctstr** `key`  **\);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString & 연산자 (lpctstr** `key`  **\);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& 연산자 (word** `key`  **\);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& 연산자 (word** `key`  **\);**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `Operator [] example: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $4A02 11`  
  
 `[Bart] = a CAge at $497E 13`  
  
##  <a name="removeall"></a>CMapStringToOb::RemoveAll  
 이 맵에서 모든 요소를 제거 하 고 제거는 `CString` key 개체입니다.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>설명  
 `CObject` 각 키에서 참조 하는 개체가 소멸 되지 않습니다. `RemoveAll` 함수 하면 확인 하지 않습니다는 참조 되는 경우 메모리 누수가 발생할 수 `CObject` 개체는 삭제 됩니다.  
  
 함수는 맵이 비어 이미 경우 제대로 작동 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::RemoveAll`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll ();**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll ();**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll ();**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll ();**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll ();**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll ();**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]  
  
##  <a name="removekey"></a>CMapStringToOb::RemoveKey  
 제공 된 키;에 해당 하는 맵 항목을 조회 그런 다음 키가 있으면 항목을 제거 합니다.  
  
```  
BOOL RemoveKey(LPCTSTR key);
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 지도 조회에 사용 되는 문자열을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 찾아 제거 되었으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 메모리 누수 경우 발생할 수 있습니다는 `CObject` 개체가 다른 위치에서 삭제 되지 않습니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::RemoveKey`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (void\***  `key` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (void\***  `key` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `RemoveKey example: A CMapStringToOb with 3 elements`  
  
 `[Marge] = a CAge at $49A0 35`  
  
 `[Homer] = a CAge at $495E 36`  
  
 `[Bart] = a CAge at $4634 13`  
  
##  <a name="setat"></a>CMapStringToOb::SetAt  
 기본 지도에 요소를 삽입 하려면 의미 합니다.  
  
```  
void SetAt(
    LPCTSTR key,  
    CObject* newValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 새 요소의 키가 문자열을 지정 합니다.  
  
 `newValue`  
 지정 된 `CObject` 포인터는 새 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
 첫째, 키가 찾습니다. 키가 있으면 해당 값이 변경 됩니다; 그런 다음 그렇지 않으면 새 키-값 요소가 만들어집니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CMapStringToOb::SetAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**SetAt void (void\***  `key` **, void\***  `newValue` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**SetAt void (void\***  `key` **, WORD** `newValue` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**SetAt void (LPCTSTR** `key` **, void\***  `newValue` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**SetAt void (LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**SetAt void (WORD** `key` **, CObject\***  `newValue` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**SetAt void (WORD** `key` **, void\***  `newValue` **);**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `before Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $493C 11`  
  
 `[Bart] = a CAge at $4654 13`  
  
 `after Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $49C0 12`  
  
 `[Bart] = a CAge at $4654 13`  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr 클래스](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord 클래스](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr 클래스](../../mfc/reference/cmapstringtoptr-class.md)   
 [CMapStringToString 클래스](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb 클래스](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr 클래스](../../mfc/reference/cmapwordtoptr-class.md)
