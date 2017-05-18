---
title: "CObList 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], lists of
- CObList class
- lists, object
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: dc95f76be56f00f4779724facaf668a72b3d5ed6
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="coblist-class"></a>CObList 클래스
순서가 지정 된 고유 하지 않은 인덱스의 목록을 fSupports `CObject` 포인터에 액세스할 수 있는 순차적으로 또는 포인터 값입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CObList : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CObList::CObList](#coblist)|에 대 한 빈 목록을 생성 `CObject` 포인터입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CObList::AddHead](#addhead)|(새 헤드는) 목록 헤드에 요소 (또는 다른 목록에 있는 모든 요소)를 추가 합니다.|  
|[CObList::AddTail](#addtail)|(새 비상 로그는) 목록의 끝에 요소 (또는 다른 목록에 있는 모든 요소)를 추가 합니다.|  
|[CObList::Find](#find)|포인터 값으로 지정 된 요소의 위치를 가져옵니다.|  
|[CObList::FindIndex](#findindex)|인덱스는&0;부터 시작 하 여 지정 된 요소의 위치를 가져옵니다.|  
|[CObList::GetAt](#getat)|지정된 된 위치에 요소를 가져옵니다.|  
|[CObList::GetCount](#getcount)|이 목록의 요소 수를 반환합니다.|  
|[CObList::GetHead](#gethead)|목록 (비어 있을 수 없습니다)의 head 요소를 반환 합니다.|  
|[CObList::GetHeadPosition](#getheadposition)|목록 헤드 요소의 위치를 반환합니다.|  
|[CObList::GetNext](#getnext)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CObList::GetPrev](#getprev)|반복에 대 한 이전 요소를 가져옵니다.|  
|[CObList::GetSize](#getsize)|이 목록의 요소 수를 반환합니다.|  
|[CObList::GetTail](#gettail)|(비워 둘 수 없습니다) 목록의 꼬리 요소를 반환 합니다.|  
|[CObList::GetTailPosition](#gettailposition)|목록의 꼬리 요소의 위치를 반환합니다.|  
|[CObList::InsertAfter](#insertafter)|지정된 된 위치에 다음 새 요소를 삽입합니다.|  
|[CObList::InsertBefore](#insertbefore)|지정된 된 위치 앞에 새 요소를 삽입합니다.|  
|[CObList::IsEmpty](#isempty)|빈 목록 조건 (요소 없음)에 대해 테스트 합니다.|  
|[CObList::RemoveAll](#removeall)|이 목록에서 모든 요소를 제거합니다.|  
|[CObList::RemoveAt](#removeat)|위치에 지정 된이 목록에서 요소를 제거 합니다.|  
|[CObList::RemoveHead](#removehead)|목록의 시작에서 요소를 제거 합니다.|  
|[CObList::RemoveTail](#removetail)|목록 꼬리에서 요소를 제거 합니다.|  
|[CObList::SetAt](#setat)|지정된 된 위치에 요소를 설정 합니다.|  
  
## <a name="remarks"></a>주의  
 `CObList`목록 이중 연결 목록 처럼 작동합니다.  
  
 형식의 변수 **위치** 목록에 대 한 키입니다. 사용할 수는 **위치** 책갈피를 저장할 위치와으로 순차적으로 목록을 순회 하는 반복기 변수. 하지만 위치가 않습니다 인덱스와 동일.  
  
 요소를 삽입이 매우 빠른 목록 헤드에 꼬리를 하 고 알려진 **위치**합니다. 순차 검색이 값 또는 인덱스 별로 요소 조회 됩니다. 이 검색 목록이 긴 경우에 느려질 수 있습니다.  
  
 `CObList`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다. 목록을 `CObject` 포인터 오버 로드 된 삽입 연산자 또는 보관에 저장 하는 `Serialize` 멤버 함수를 각각 `CObject` 요소가 차례로 serialize 됩니다.  
  
 개별 덤프가 필요한 경우 `CObject` 목록에서 요소를 1 이상으로 덤프 컨텍스트 깊이 설정 해야 합니다.  
  
 경우는 `CObList` 개체를 삭제 하거나 때 해당 요소를 제거 하면만 `CObject` 참조 하는 개체, 포인터 제거 됩니다.  
  
 고유한 클래스를 파생할 수 `CObList`합니다. 새 목록 클래스에서 파생 된 개체에 대 한 포인터를 보유 하도록 설계 `CObject`, 새 데이터 멤버를 추가 하는 새 멤버 함수입니다. 결과 목록 않음을 유의 엄격 하 게 형식이 안전한의 삽입을 허용 하기 때문에 `CObject` 포인터입니다.  
  
> [!NOTE]
>  사용 해야는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 목록을 serialize 하려는 경우 파생 된 클래스의 구현에는 매크로입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CObList`, 문서를 참조 하십시오 [컬렉션](../../mfc/collections.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcoll.h  
  
##  <a name="addhead"></a>CObList::AddHead  
 이 목록의 헤드에 새 요소 또는 요소 목록을 추가합니다.  
  
```  
POSITION AddHead(CObject* newElement);  
void AddHead(CObList* pNewList);
```  
  
### <a name="parameters"></a>매개 변수  
 `newElement`  
 `CObject` 이 목록에 추가할 수에 대 한 포인터입니다.  
  
 `pNewList`  
 에 대 한 포인터를 다른 `CObList` 목록입니다. 요소 `pNewList` 이 목록에 추가 됩니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 버전은 반환 된 **위치** 새로 삽입된 된 요소의 값입니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::AddHead`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**위치 AddHead (void\* ** `newElement` **);**<br /><br /> **AddHead void (해당 클래스가\* ** `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 AddHead (const CString / /** `newElement` **);**<br /><br /> **위치 AddHead (LPCTSTR** `newElement` **);**<br /><br /> **AddHead void (CStringList\* ** `pNewList` **);**|  
  
### <a name="remarks"></a>주의  
 목록 작업 전에 비어 있을 수 있습니다.  
  
### <a name="example"></a>예제  
  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&89;](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]  
  
 이 프로그램의 결과 다음과 같습니다.  
  
 `AddHead example: A CObList with 2 elements`  
  
 `a CAge at $44A8 40`  
  
 `a CAge at $442A 21`  
  
##  <a name="addtail"></a>CObList::AddTail  
 이 목록의 꼬리에 요소 목록이 나 새 요소를 추가합니다.  
  
```  
POSITION AddTail(CObject* newElement);  
void AddTail(CObList* pNewList);
```  
  
### <a name="parameters"></a>매개 변수  
 `newElement`  
 `CObject` 이 목록에 추가할 수에 대 한 포인터입니다.  
  
 `pNewList`  
 에 대 한 포인터를 다른 `CObList` 목록입니다. 요소 `pNewList` 이 목록에 추가 됩니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 버전은 반환 된 **위치** 새로 삽입된 된 요소의 값입니다.  
  
### <a name="remarks"></a>주의  
 목록 작업 전에 비어 있을 수 있습니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::AddTail`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**위치 AddTail (void\* ** `newElement` **);**<br /><br /> **AddTail void (해당 클래스가\* ** `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 AddTail (const CString / /** `newElement` **);**<br /><br /> **위치 AddTail (LPCTSTR** `newElement` **);**<br /><br /> **AddTail void (CStringList\* ** `pNewList` **);**|  
  
### <a name="example"></a>예제  
  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&90;](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]  
  
 이 프로그램의 결과 다음과 같습니다.  
  
 `AddTail example: A CObList with 2 elements`  
  
 `a CAge at $444A 21`  
  
 `a CAge at $4526 40`  
  
##  <a name="coblist"></a>CObList::CObList  
 빈 생성 `CObject` 포인터 목록입니다.  
  
```  
CObList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 목록을 확장 하는 것에 대 한 메모리 할당 세분성입니다.  
  
### <a name="remarks"></a>주의  
 단위에서 메모리를 할당 목록 늘어나면 `nBlockSize` 항목입니다. 메모리 할당이 실패 하면는 `CMemoryException` throw 됩니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::CObList`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**해당 클래스가 (INT_PTR** `nBlockSize` **= 10).**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10).**|  
  
### <a name="example"></a>예제  
  다음의 목록은 `CObject`-파생 클래스 `CAge` 모든 컬렉션 예제에서 사용 됩니다.  
  
 [!code-cpp[NVC_MFCCollections #&91;](../../mfc/codesnippet/cpp/coblist-class_3.h)]  
  
 다음은 예의 `CObList` 생성자 사용:  
  
 [!code-cpp[NVC_MFCCollections #&92;](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]  
  
##  <a name="find"></a>CObList::Find  
 첫 번째 찾으려고 순차적으로 목록을 검색 하는 `CObject` 일치 하는 지정 된 포인터 `CObject` 포인터입니다.  
  
```  
POSITION Find(
    CObject* searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `searchValue`  
 이 목록에 있어야 하는 개체 포인터입니다.  
  
 `startAfter`  
 검색 시작 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 개체가 없는 경우.  
  
### <a name="remarks"></a>주의  
 포인터 값이 비교 되는 참고, 개체의 내용에 없습니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::Find`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**위치 찾기 (void\* ** `searchValue` **, 위치** `startAfter` **= NULL) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 찾기 (LPCTSTR** `searchValue` **, 위치** `startAfter` **= NULL) const;**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&93;](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]  
  
##  <a name="findindex"></a>CObList::FindIndex  
 값을 사용 하 여 `nIndex` 목록의 인덱스입니다.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 찾아내야 목록 요소의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 경우 `nIndex` 너무 큽니다. (프레임 워크 경우 어설션을 생성 `nIndex` 음수입니다.)  
  
### <a name="remarks"></a>주의  
 중지 목록의 헤드에서 순차적 검색을 시작 하기는 *n*번째 요소입니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::FindIndex`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**위치 FindIndex (INT_PTR** `nIndex` **) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 FindIndex (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&94;](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]  
  
##  <a name="getat"></a>CObList::GetAt  
 형식의 변수 **위치** 목록에 대 한 키입니다.  
  
```  
CObject*& GetAt(POSITION position);  
const CObject*& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *위치*  
 A **위치** 이전에서 반환 된 값 `GetHeadPosition` 또는 **찾을** 멤버 함수 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값에 대 한 설명을 참조 [GetHead](#gethead)합니다.  
  
### <a name="remarks"></a>주의  
 작업할 수 없습니다.와 인덱스를 동일 하지 않으며는 **위치** 직접 값입니다. `GetAt`검색 된 `CObject` 지정된 된 위치와 연결 된 포인터입니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 올바르지 않을 경우 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**const void\*GetAt / / (위치** *위치* **) const;**<br /><br /> **void\*GetAt / / (위치** *위치* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString / / GetAt (위치** *위치* **) const;**<br /><br /> **CString / / GetAt (위치** *위치* **);**|  
  
### <a name="example"></a>예제  
  예를 참조 [FindIndex](#findindex)합니다.  
  
##  <a name="getcount"></a>CObList::GetCount  
 이 목록의 요소 수를 가져옵니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 요소 수를 포함 하는 정수 값입니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetCount`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**Const; INT_PTR GetCount)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&95;](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]  
  
##  <a name="gethead"></a>CObList::GetHead  
 가져옵니다는 `CObject` 이 그룹의 head 요소를 나타내는 포인터입니다.  
  
```  
CObject*& GetHead();  
const CObject*& GetHead() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록에 대 한 포인터를 통해 액세스 하는 경우는 **const CObList**, 다음 `GetHead` 반환는 `CObject` 포인터입니다. 함수는 대입문의 오른쪽에만 사용할 수 있으며 이므로 목록 수정 되지 않도록에서 보호 합니다.  
  
 목록에 대 한 포인터를 통해 또는 직접 액세스 하는 경우는 `CObList`, 다음 `GetHead` 반환에 대 한 참조는 `CObject` 포인터입니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `GetHead`합니다. 목록이 비어 있으면 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 요소는 목록에 포함 되어 있는지 확인 합니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetHead`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**const void\*GetHead () / / const; void\*GetHead (); / /**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const; const CString / / GetHead) CString / / GetHead ();**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 다음 예제에서는 `GetHead` 대입문의 왼쪽에 있습니다.  
  
 [!code-cpp[NVC_MFCCollections #&96;](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]  
  
##  <a name="getheadposition"></a>CObList::GetHeadPosition  
 이 그룹의 head 요소 위치를 가져옵니다.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 목록이 비어 있는 경우.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetHeadPosition`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**Const; 위치 GetHeadPosition)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; 위치 GetHeadPosition)**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&97;](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]  
  
##  <a name="getnext"></a>CObList::GetNext  
 로 식별 되는 목록 요소를 가져옵니다 `rPosition`, 다음 설정 `rPosition` 에 `POSITION` 목록에서 다음 항목의 값입니다.  
  
```  
CObject*& GetNext(POSITION& rPosition);  
const CObject* GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `rPosition`  
 에 대 한 참조는 `POSITION` 이전에서 반환 된 값 `GetNext`, `GetHeadPosition`, 또는 기타 멤버 함수 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값에 대 한 설명을 참조 [GetHead](#gethead)합니다.  
  
### <a name="remarks"></a>주의  
 사용할 수 있습니다 `GetNext` 정방향 반복 루프를 호출 하 여 초기 위치를 설정 하는 경우에 `GetHeadPosition` 또는 `Find`합니다.  
  
 확인 해야 하면 `POSITION` 값 목록에서 올바른 위치를 나타냅니다. 올바르지 않을 경우 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다.  
  
 검색 된 요소가 있으면 목록에서 마지막 다음의 새 값 `rPosition` 로 설정 된 `NULL`합니다.  
  
 반복 하는 동안 요소를 제거 하는 것이 불가능 합니다. 예를 참조 [RemoveAt](#removeat)합니다.  
  
> [!NOTE]
>  이 메서드의 const 버전 반환할 변경 된 MFC 8.0부터 `const CObject*` 대신 `const CObject*&`합니다.  컴파일러를 표준 c + +를 준수 상태로 변경 되었습니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetNext`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>예제  
  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&98;](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]  
  
 이 프로그램의 결과 다음과 같습니다.  
  
 `a CAge at $479C 40`  
  
 `a CAge at $46C0 21`  
  
##  <a name="getprev"></a>CObList::GetPrev  
 로 식별 되는 목록 요소를 가져옵니다 `rPosition`, 다음 설정 `rPosition` 에 `POSITION` 목록에서 이전 항목의 값입니다.  
  
```  
CObject*& GetPrev(POSITION& rPosition);  
const CObject* GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `rPosition`  
 에 대 한 참조는 `POSITION` 이전에서 반환 된 값 `GetPrev` 또는 다른 멤버 함수 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값에 대 한 설명을 참조 [GetHead](#gethead)합니다.  
  
### <a name="remarks"></a>주의  
 사용할 수 있습니다 `GetPrev` 를 호출 하 여 초기 위치를 설정 하는 경우 역방향 반복 루프에서 `GetTailPosition` 또는 `Find`합니다.  
  
 확인 해야 하면 `POSITION` 값 목록에서 올바른 위치를 나타냅니다. 올바르지 않을 경우 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다.  
  
 검색 된 요소가 있으면 목록에서 첫 번째 다음의 새 값 `rPosition` 로 설정 된 `NULL`합니다.  
  
> [!NOTE]
>  이 메서드의 const 버전 반환할 변경 된 MFC 8.0부터 `const CObject*` 대신 `const CObject*&`합니다.  컴파일러를 표준 c + +를 준수 상태로 변경 되었습니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetPrev`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>예제  
  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&99;](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]  
  
 이 프로그램의 결과 다음과 같습니다.  
  
 `a CAge at $421C 21`  
  
 `a CAge at $421C 40`  
  
##  <a name="getsize"></a>CObList::GetSize  
 목록의 요소 수를 반환합니다.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록의 항목 수입니다.  
  
### <a name="remarks"></a>주의  
 목록에 있는 요소의 수를 검색 하려면이 메서드를 호출 합니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetSize`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**Const; INT_PTR GetSize)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&100;](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]  
  
##  <a name="gettail"></a>CObList::GetTail  
 가져옵니다는 `CObject` 이 목록의 꼬리 요소를 나타내는 포인터입니다.  
  
```  
CObject*& GetTail();  
const CObject*& GetTail() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 값에 대 한 설명을 참조 [GetHead](#gethead)합니다.  
  
### <a name="remarks"></a>주의  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `GetTail`합니다. 목록이 비어 있으면 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 요소는 목록에 포함 되어 있는지 확인 합니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetTail`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**const void\*GetTail () / / const; void\*GetTail (); / /**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const; const CString / / GetTail) CString / / GetTail ();**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&101;](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]  
  
##  <a name="gettailposition"></a>CObList::GetTailPosition  
 이 목록의; 꼬리 요소 위치를 가져옵니다. **NULL** 목록이 비어 있는 경우.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 목록이 비어 있는 경우.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::GetTailPosition`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**Const; 위치 GetTailPosition)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; 위치 GetTailPosition)**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&102;](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]  
  
##  <a name="insertafter"></a>CObList::InsertAfter  
 지정된 된 위치에 요소 뒤를이 목록에 요소를 추가 합니다.  
  
```  
POSITION InsertAfter(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 *위치*  
 이전 **,** 또는 `GetNext`Find `GetPrev`멤버 함수 호출에서 반환된 **POSITION** 값입니다.  
  
 `newElement`  
 이 목록에 추가할 개체 포인터입니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::InsertAfter`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**위치 InsertAfter (위치** *위치* **, void\* ** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 InsertAfter (위치** *위치* **, const CString / /** `newElement` **);**<br /><br /> **위치 InsertAfter (위치** *위치* **, LPCTSTR** `newElement` **);**|  
  
### <a name="return-value"></a>반환 값  
 A **위치** 동일한 값으로는 *위치* 매개 변수입니다.  
  
### <a name="example"></a>예제  
  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&103;](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]  
  
 이 프로그램의 결과 다음과 같습니다.  
  
 `InsertAfter example: A CObList with 3 elements`  
  
 `a CAge at $4A44 40`  
  
 `a CAge at $4A64 65`  
  
 `a CAge at $4968 21`  
  
##  <a name="insertbefore"></a>CObList::InsertBefore  
 이 목록에서 지정된 위치의 요소 앞에 요소를 추가합니다.  
  
```  
POSITION InsertBefore(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 *위치*  
 이전 **,** 또는 `GetNext`Find `GetPrev`멤버 함수 호출에서 반환된 **POSITION** 값입니다.  
  
 `newElement`  
 이 목록에 추가할 개체 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 목록이 비어 있는 경우.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::InsertBefore`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**위치 InsertBefore (위치** *위치* **, void\* ** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 InsertBefore (위치** *위치* **, const CString / /** `newElement` **);**<br /><br /> **위치 InsertBefore (위치** *위치* **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>예제  
  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&104;](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]  
  
 이 프로그램의 결과 다음과 같습니다.  
  
 `InsertBefore example: A CObList with 3 elements`  
  
 `a CAge at $4AE2 40`  
  
 `a CAge at $4B02 65`  
  
 `a CAge at $49E6 21`  
  
##  <a name="isempty"></a>CObList::IsEmpty  
 이 목록에 요소가 있는지 여부를 나타냅니다.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 목록이 비어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::IsEmpty`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**Const; BOOL IsEmpty)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; BOOL IsEmpty)**|  
  
### <a name="example"></a>예제  
  예를 참조 [RemoveAll](#removeall)합니다.  
  
##  <a name="removeall"></a>CObList::RemoveAll  
 이 목록에서 모든 요소를 제거 하 고 연결 된 해제 `CObList` 메모리입니다.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>주의  
 목록이 비어 이미 있으면 오류가 생성 됩니다.  
  
 요소를 제거 하는 경우는 `CObList`, 목록에서 개체 포인터를 제거 합니다. 것은 개체 자체를 삭제 하려면 사용자의 책임입니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::RemoveAll`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**void RemoveAll ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll ();**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&105;](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]  
  
##  <a name="removeat"></a>CObList::RemoveAt  
 이 목록에서 지정된 된 요소를 제거합니다.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>매개 변수  
 *위치*  
 목록에서 제거할 요소의 위치입니다.  
  
### <a name="remarks"></a>주의  
 요소를 제거 하는 경우는 `CObList`, 목록에서 개체 포인터를 제거 합니다. 것은 개체 자체를 삭제 하려면 사용자의 책임입니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 올바르지 않을 경우 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::RemoveAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**RemoveAt void (위치** *위치* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**RemoveAt void (위치** *위치* **);**|  
  
### <a name="example"></a>예제  
  목록 반복 하는 동안 요소를 제거할 때 주의 해야 합니다. 다음 예에서는 유효한 보장 하는 제거 기술 **위치** 에 대 한 값 [GetNext](#getnext)합니다.  
  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&106;](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]  
  
 이 프로그램의 결과 다음과 같습니다.  
  
 `RemoveAt example: A CObList with 2 elements`  
  
 `a CAge at $4C1E 65`  
  
 `a CAge at $4B22 21`  
  
##  <a name="removehead"></a>CObList::RemoveHead  
 목록의 시작에서 요소를 제거 하 고에 대 한 포인터를 반환 합니다.  
  
```  
CObject* RemoveHead();
```  
  
### <a name="return-value"></a>반환 값  
 `CObject` 목록 헤드에 이전에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveHead`합니다. 목록이 비어 있으면 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 요소는 목록에 포함 되어 있는지 확인 합니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::RemoveHead`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&107;](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]  
  
##  <a name="removetail"></a>CObList::RemoveTail  
 목록 꼬리에서 요소를 제거 하 고에 대 한 포인터를 반환 합니다.  
  
```  
CObject* RemoveTail();
```  
  
### <a name="return-value"></a>반환 값  
 목록의 끝에 있는 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveTail`합니다. 목록이 비어 있으면 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 요소는 목록에 포함 되어 있는지 확인 합니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::RemoveTail`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|  
  
### <a name="example"></a>예제  
 참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&108;](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]  
  
##  <a name="setat"></a>CObList::SetAt  
 지정된 된 위치에 요소를 설정 합니다.  
  
```  
void SetAt(
    POSITION pos,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 **위치** 설정할 요소입니다.  
  
 `newElement`  
 `CObject` 목록에 쓸 수에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 형식의 변수 **위치** 목록에 대 한 키입니다. 작업할 수 없습니다.와 인덱스를 동일 하지 않으며는 **위치** 직접 값입니다. `SetAt`기록 된 `CObject` 목록에 지정된 된 위치에 대 한 포인터입니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 올바르지 않을 경우 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다.  
  
 다음 표에서 다른 멤버와 비슷한 함수 `CObList::SetAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[해당 클래스가](../../mfc/reference/cptrlist-class.md)|**SetAt void (위치** `pos` **, const CString / /** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt( POSITION** `pos` **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>예제  
  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections #&109;](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]  
  
 이 프로그램의 결과 다음과 같습니다.  
  
 `SetAt example: A CObList with 2 elements`  
  
 `a CAge at $4D98 40`  
  
 `a CAge at $4DB8 65`  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CStringList 클래스](../../mfc/reference/cstringlist-class.md)   
 [해당 클래스가 클래스](../../mfc/reference/cptrlist-class.md)

