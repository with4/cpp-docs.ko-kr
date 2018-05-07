---
title: CList 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CList
- AFXTEMPL/CList
- AFXTEMPL/CList::CList
- AFXTEMPL/CList::AddHead
- AFXTEMPL/CList::AddTail
- AFXTEMPL/CList::Find
- AFXTEMPL/CList::FindIndex
- AFXTEMPL/CList::GetAt
- AFXTEMPL/CList::GetCount
- AFXTEMPL/CList::GetHead
- AFXTEMPL/CList::GetHeadPosition
- AFXTEMPL/CList::GetNext
- AFXTEMPL/CList::GetPrev
- AFXTEMPL/CList::GetSize
- AFXTEMPL/CList::GetTail
- AFXTEMPL/CList::GetTailPosition
- AFXTEMPL/CList::InsertAfter
- AFXTEMPL/CList::InsertBefore
- AFXTEMPL/CList::IsEmpty
- AFXTEMPL/CList::RemoveAll
- AFXTEMPL/CList::RemoveAt
- AFXTEMPL/CList::RemoveHead
- AFXTEMPL/CList::RemoveTail
- AFXTEMPL/CList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CList [MFC], CList
- CList [MFC], AddHead
- CList [MFC], AddTail
- CList [MFC], Find
- CList [MFC], FindIndex
- CList [MFC], GetAt
- CList [MFC], GetCount
- CList [MFC], GetHead
- CList [MFC], GetHeadPosition
- CList [MFC], GetNext
- CList [MFC], GetPrev
- CList [MFC], GetSize
- CList [MFC], GetTail
- CList [MFC], GetTailPosition
- CList [MFC], InsertAfter
- CList [MFC], InsertBefore
- CList [MFC], IsEmpty
- CList [MFC], RemoveAll
- CList [MFC], RemoveAt
- CList [MFC], RemoveHead
- CList [MFC], RemoveTail
- CList [MFC], SetAt
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2a84e73c165efd8f2f17e66af149e33d90395e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="clist-class"></a>CList 클래스
순차적으로 또는 값별로 액세스할 수 있고 고유하지 않은 개체의 순서가 지정된 목록을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class TYPE, class ARG_TYPE = const TYPE&>  
class CList : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CList::CList](#clist)|정렬된 된 빈 목록을 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CList::AddHead](#addhead)|(새 헤드는) 목록 헤드에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|  
|[CList::AddTail](#addtail)|(새 비상은) 목록의 끝에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|  
|[CList::Find](#find)|포인터 값으로 지정 된 요소의 위치를 가져옵니다.|  
|[CList::FindIndex](#findindex)|0 기반 인덱스에서 지정한 요소의 위치를 가져옵니다.|  
|[CList::GetAt](#getat)|지정된 된 위치에 요소를 가져옵니다.|  
|[CList::GetCount](#getcount)|이 목록의 요소 수를 반환합니다.|  
|[CList::GetHead](#gethead)|목록 (비어 있을 수 없습니다)의 head 요소를 반환 합니다.|  
|[CList::GetHeadPosition](#getheadposition)|목록 헤드 요소의 위치를 반환합니다.|  
|[CList::GetNext](#getnext)|반복 하는 데 다음 요소를 가져옵니다.|  
|[CList::GetPrev](#getprev)|반복 하는 데 이전 요소를 가져옵니다.|  
|[CList::GetSize](#getsize)|이 목록의 요소 수를 반환합니다.|  
|[CList::GetTail](#gettail)|(비어 있을 수 없습니다) 목록의 꼬리 요소를 반환 합니다.|  
|[CList::GetTailPosition](#gettailposition)|목록의 꼬리 요소의 위치를 반환합니다.|  
|[CList::InsertAfter](#insertafter)|지정된 된 위치 뒤 새 요소를 삽입합니다.|  
|[CList::InsertBefore](#insertbefore)|지정된 된 위치 앞에 새 요소를 삽입합니다.|  
|[CList::IsEmpty](#isempty)|빈 목록 조건 (요소 없음)에 대해 테스트 합니다.|  
|[CList::RemoveAll](#removeall)|이 목록에서 모든 요소를 제거합니다.|  
|[CList::RemoveAt](#removeat)|위치에 지정 된이 목록에서 요소를 제거 합니다.|  
|[CList::RemoveHead](#removehead)|목록의 시작에서 요소를 제거 합니다.|  
|[CList::RemoveTail](#removetail)|목록 꼬리에서 요소를 제거 합니다.|  
|[CList::SetAt](#setat)|지정된 된 위치에 요소를 설정 합니다.|  
  
#### <a name="parameters"></a>매개 변수  
 `TYPE`  
 목록에 저장 된 개체의 형식입니다.  
  
 `ARG` *_* `TYPE`  
 목록에 저장 된 개체를 참조 하는 데 사용 하는 형식입니다. 참조일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `CList` 이중 연결 목록 처럼 동작합니다.  
  
 형식의 변수 **위치** 목록에 대 한 키입니다. 사용할 수는 **위치** 책갈피를 저장할 위치와 순서 대로 목록을 순회 하는 반복기로 변수입니다. 그러나 위치는 같지 않습니다 한 인덱스로 합니다.  
  
 요소를 삽입은 아주 목록 헤드에 빠른, 꼬리, 및 알려진 **위치**합니다. 순차 검색이 값 또는 인덱스 별로 요소를 조회 해야 합니다. 이 검색 목록이 긴 경우에 느려질 수 있습니다.  
  
 목록에서 개별 요소의 덤프가 필요한 경우 덤프 컨텍스트 깊이 1 이상으로 설정 해야 합니다.  
  
 글로벌 도우미 함수를이 클래스 호출의 특정 멤버 함수는 대부분 용도에 대 한 사용자 지정 되어야 합니다는 `CList` 클래스입니다. 참조 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) "매크로 및 전역 변수" 섹션에 있습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CList`, 문서를 참조 [컬렉션](../../mfc/collections.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtempl.h  
  
##  <a name="addhead"></a>  CList::AddHead  
 이 목록 헤드에 새 요소 또는 요소의 목록을 추가합니다.  
  
```  
POSITION AddHead(ARG_TYPE newElement);  
void AddHead(CList* pNewList);
```  
  
### <a name="parameters"></a>매개 변수  
 `ARG_TYPE`  
 목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).  
  
 `newElement`  
 새 요소입니다.  
  
 `pNewList`  
 에 대 한 포인터를 다른 `CList` 목록입니다. 요소 `pNewList` 이 목록에 추가 됩니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 버전은 반환 된 **위치** 새로 삽입된 된 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
 목록 작업 전에 비어 있을 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]  
  
##  <a name="addtail"></a>  CList::AddTail  
 이 목록의 꼬리에 새 요소 또는 요소의 목록을 추가합니다.  
  
```  
POSITION AddTail(ARG_TYPE newElement);  
void AddTail(CList* pNewList);
```  
  
### <a name="parameters"></a>매개 변수  
 `ARG_TYPE`  
 목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).  
  
 `newElement`  
 이 목록에 추가할 요소입니다.  
  
 `pNewList`  
 에 대 한 포인터를 다른 `CList` 목록입니다. 요소 `pNewList` 이 목록에 추가 됩니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 버전은 반환 된 **위치** 새로 삽입된 된 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
 목록 작업 전에 비어 있을 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]  
  
##  <a name="clist"></a>  CList::CList  
 정렬된 된 빈 목록을 생성합니다.  
  
```  
CList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 목록 확장에 대 한 메모리 할당 세분성을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 단위에서 메모리를 할당 목록까지 확장 되면서 `nBlockSize` 항목입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]  
  
##  <a name="find"></a>  CList::Find  
 지정 된 일치 하는 첫 번째 요소를 찾을 수 순차적 목록을 검색 하는 `searchValue`합니다.  
  
```  
POSITION Find(
    ARG_TYPE searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `ARG_TYPE`  
 목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).  
  
 `searchValue`  
 목록에서 찾으려는 값입니다.  
  
 `startAfter`  
 검색 시작 위치입니다. 지정은 값이 없으면 head 요소와 검색을 시작 합니다.  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 개체가 없는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]  
  
##  <a name="findindex"></a>  CList::FindIndex  
 값을 사용 하 여 `nIndex` 목록의 인덱스입니다.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 찾을 목록 요소의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 경우 `nIndex` 가 음수 이거나 너무 큽니다.  
  
### <a name="remarks"></a>설명  
 중지 목록의 헤드에서 순차적 검색을 시작 하기는 *n*번째 요소입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]  
  
##  <a name="getat"></a>  CList::GetAt  
 지정 된 위치의 목록 요소를 가져옵니다.  
  
```  
TYPE& GetAt(POSITION position);  
const TYPE& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수를 목록에서 개체의 유형을 지정 합니다.  
  
 *위치*  
 목록에서 가져올 요소의 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 반환 값 설명을 참조 `GetHead`합니다.  
  
### <a name="remarks"></a>설명  
 `GetAt` 지정된 된 위치와 연결 된 요소 (또는 요소에 대 한 참조)를 반환 합니다. 인덱스를 동일 하지 않습니다 및 작업할 수 없습니다. 한 **위치** 직접 값입니다. 형식의 변수 **위치** 목록에 대 한 키입니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CList::GetHeadPosition](#getheadposition)합니다.  
  
##  <a name="getcount"></a>  CList::GetCount  
 이 목록의 요소 수를 가져옵니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 요소를 포함 하는 정수 값입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 하면 동일한 결과를 생성 합니다는 [CList::GetSize](#getsize) 메서드.  
  
### <a name="example"></a>예제  
  예를 참조 [CList::RemoveHead](#removehead)합니다.  
  
##  <a name="gethead"></a>  CList::GetHead  
 이 목록의 head 요소 (또는 head 요소에 대 한 참조)를 가져옵니다.  
  
```  
const TYPE& GetHead() const;  
  
TYPE& GetHead();
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수를 목록에서 개체의 유형을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록이 **const**, `GetHead` 목록 헤드에 있는 요소의 복사본을 반환 합니다. 이 함수를 대입문의 오른쪽에만 사용할 수 있도록 하며 수정 되지 않도록에서 목록을 보호 합니다.  
  
 목록 없으면 **const**, `GetHead` 목록 헤드에 있는 요소에 대 한 참조를 반환 합니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `GetHead`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 목록 요소에 포함 되었는지 확인 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]  
  
##  <a name="getheadposition"></a>  CList::GetHeadPosition  
 이 목록의 head 요소 위치를 가져옵니다.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 목록이 비어 있는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]  
  
##  <a name="getnext"></a>  CList::GetNext  
 로 식별 되는 목록 요소를 가져옵니다 `rPosition`, 다음 설정 `rPosition` 에 **위치** 목록에서 다음 항목의 값입니다.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
const TYPE& GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수를 목록에서 요소의 형식을 지정 합니다.  
  
 `rPosition`  
 에 대 한 참조는 **위치** 이전에서 반환 된 값 `GetNext`, [GetHeadPosition](#getheadposition), 또는 기타 멤버 함수 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록이 **const**, `GetNext` 목록의 요소의 복사본을 반환 합니다. 이 함수를 대입문의 오른쪽에만 사용할 수 있도록 하며 수정 되지 않도록에서 목록을 보호 합니다.  
  
 목록 없으면 **const**, `GetNext` 목록의 요소에 대 한 참조를 반환 합니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 사용할 수 있습니다 `GetNext` 정방향으로 반복 루프를 호출 하 여 초기 위치를 설정 하는 경우에 `GetHeadPosition` 또는 **찾을**합니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
 검색된 된 요소는 목록에서 마지막 다음 새 값의 경우 `rPosition` 로 설정 된 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]  
  
##  <a name="getprev"></a>  CList::GetPrev  
 로 식별 되는 목록 요소를 가져옵니다 `rPosition`, 다음 설정 `rPosition` 에 **위치** 목록에서 이전 항목의 값입니다.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
const TYPE& GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수를 목록에서 요소의 형식을 지정 합니다.  
  
 `rPosition`  
 에 대 한 참조는 **위치** 이전에서 반환 된 값 `GetPrev` 또는 다른 멤버 함수 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록이 **const**, `GetPrev` 목록 헤드에 있는 요소의 복사본을 반환 합니다. 이 함수를 대입문의 오른쪽에만 사용할 수 있도록 하며 수정 되지 않도록에서 목록을 보호 합니다.  
  
 목록 없으면 **const**, `GetPrev` 목록의 요소에 대 한 참조를 반환 합니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 사용할 수 있습니다 `GetPrev` 을 호출 하 여 초기 위치를 설정 하는 경우 역방향 반복 루프에서 `GetTailPosition` 또는 **찾을**합니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
 검색된 된 요소 목록에서 첫 번째 다음의 새 값 이면의 `rPosition` 로 설정 된 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]  
  
##  <a name="getsize"></a>  CList::GetSize  
 목록 요소의 수를 반환합니다.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록의 항목 수입니다.  
  
### <a name="remarks"></a>설명  
 목록에 있는 요소의 수를 검색 하려면이 메서드를 호출 합니다.  이 메서드를 호출 하면 동일한 결과를 생성 합니다는 [CList::GetCount](#getcount) 메서드.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]  
  
##  <a name="gettail"></a>  CList::GetTail  
 가져옵니다는 `CObject` 이 목록의 꼬리 요소를 나타내는 포인터입니다.  
  
```  
TYPE& GetTail();  
const TYPE& GetTail() const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 목록에서 요소 형식을 지정 하는 템플릿 매개 변수  
  
### <a name="return-value"></a>반환 값  
 에 대 한 반환 값 설명을 참조 [GetHead](../../mfc/reference/coblist-class.md#gethead)합니다.  
  
### <a name="remarks"></a>설명  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `GetTail`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 포함 되었는지 확인 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]  
  
##  <a name="gettailposition"></a>  CList::GetTailPosition  
 이 목록의; 비상 요소의 위치를 가져옵니다. **NULL** 목록이 비어 있는 경우.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 목록이 비어 있는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]  
  
##  <a name="insertafter"></a>  CList::InsertAfter  
 이 목록에 지정된 된 위치에 요소 뒤 요소를 추가 합니다.  
  
```  
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 *위치*  
 이전 **,** 또는 `GetNext`Find `GetPrev`멤버 함수 호출에서 반환된 **POSITION** 값입니다.  
  
 `ARG_TYPE`  
 목록 요소의 형식을 지정 하는 템플릿 매개 변수  
  
 `newElement`  
 이 목록에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 반복 또는 목록 요소 검색에 사용할 수 있는 **POSITION** 값입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]  
  
##  <a name="insertbefore"></a>  CList::InsertBefore  
 이 목록에서 지정된 위치의 요소 앞에 요소를 추가합니다.  
  
```  
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 *위치*  
 이전 **,** 또는 `GetNext`Find `GetPrev`멤버 함수 호출에서 반환된 **POSITION** 값입니다.  
  
 `ARG_TYPE`  
 목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).  
  
 `newElement`  
 이 목록에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 반복 또는 목록 요소 검색에 사용할 수 있는 **POSITION** 값입니다.  
  
### <a name="remarks"></a>설명  
 *position* 이 **NULL**이면 요소가 목록의 처음 부분에 삽입됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]  
  
##  <a name="isempty"></a>  CList::IsEmpty  
 이 목록에 요소가 있는지 여부를 나타냅니다.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 목록은 비어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]  
  
##  <a name="removeall"></a>  CList::RemoveAll  
 이 목록에서 모든 요소를 제거 하 고 관련 된 메모리를 해제 합니다.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>설명  
 목록이 비어 이미 하는 경우 오류가 생성 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]  
  
##  <a name="removeat"></a>  CList::RemoveAt  
 이 목록에서 지정된 된 요소를 제거합니다.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>매개 변수  
 *위치*  
 목록에서 제거할 요소의 위치입니다.  
  
### <a name="remarks"></a>설명  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]  
  
##  <a name="removehead"></a>  CList::RemoveHead  
 목록의 시작에서 요소를 제거 하 고에 대 한 포인터를 반환 합니다.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 목록에서 요소 형식을 지정 하는 템플릿 매개 변수  
  
### <a name="return-value"></a>반환 값  
 이전에 목록의 맨 처음에 요소입니다.  
  
### <a name="remarks"></a>설명  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveHead`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 목록 요소에 포함 되었는지 확인 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]  
  
##  <a name="removetail"></a>  CList::RemoveTail  
 목록 꼬리에서 요소를 제거 하 고에 대 한 포인터를 반환 합니다.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 목록에서 요소 형식을 지정 하는 템플릿 매개 변수  
  
### <a name="return-value"></a>반환 값  
 목록의 끝에 있는 요소입니다.  
  
### <a name="remarks"></a>설명  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveTail`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 목록 요소에 포함 되었는지 확인 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]  
  
##  <a name="setat"></a>  CList::SetAt  
 형식의 변수 **위치** 목록에 대 한 키입니다.  
  
```  
void SetAt(POSITION pos, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 **위치** 설정할 요소입니다.  
  
 `ARG_TYPE`  
 목록 요소의 형식을 지정하는 템플릿 매개 변수입니다(참조일 수 있음).  
  
 `newElement`  
 목록에 추가할 요소입니다.  
  
### <a name="remarks"></a>설명  
 인덱스를 동일 하지 않습니다 및 작업할 수 없습니다. 한 **위치** 직접 값입니다. `SetAt` 목록에서 지정된 된 위치에 요소를 씁니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMap 클래스](../../mfc/reference/cmap-class.md)   
 [CArray 클래스](../../mfc/reference/carray-class.md)
