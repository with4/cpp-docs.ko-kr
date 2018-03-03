---
title: "CAtlList 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
dev_langs:
- C++
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13d26ba7107e21e64ad65ec53264b4f3740fd13a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catllist-class"></a>CAtlList 클래스
이 클래스는 만들고 목록 개체를 관리 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename E, class ETraits = CElementTraits<E>>  
class CAtlList
```  
  
#### <a name="parameters"></a>매개 변수  
 `E`  
 요소 형식입니다.  
  
 `ETraits`  
 요소 이동 하거나 복사 하는 데 사용 되는 코드입니다. 참조 [CElementTraits 클래스](../../atl/reference/celementtraits-class.md) 내용을 확인 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlList::INARGTYPE](#inargtype)||  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlList::CAtlList](#catllist)|생성자입니다.|  
|[CAtlList:: ~ CAtlList](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlList::AddHead](#addhead)|목록 헤드에 요소를 추가 하려면이 메서드를 호출 합니다.|  
|[CAtlList::AddHeadList](#addheadlist)|목록 헤드에 기존 목록에 추가 하려면이 메서드를 호출 합니다.|  
|[CAtlList::AddTail](#addtail)|이 목록의 꼬리에 요소를 추가 하려면이 메서드를 호출 합니다.|  
|[CAtlList::AddTailList](#addtaillist)|이 목록의 꼬리에 기존 목록에 추가 하려면이 메서드를 호출 합니다.|  
|[CAtlList::AssertValid](#assertvalid)|유효한 목록을 확인 하려면이 메서드를 호출 합니다.|  
|[CAtlList::Find](#find)|지정 된 요소의 목록을 검색 하려면이 메서드를 호출 합니다.|  
|[CAtlList::FindIndex](#findindex)|인덱스 값이 지정 된 요소의 위치를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlList::GetAt](#getat)|목록에서 지정된 된 위치에 있는 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetCount](#getcount)|목록에서 개체의 수를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetHead](#gethead)|목록의 처음 부분에 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetHeadPosition](#getheadposition)|목록의 시작 위치를 가져오는이 메서드를 호출 합니다.|  
|[CAtlList::GetNext](#getnext)|목록에서 다음 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetPrev](#getprev)|목록에서 이전 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetTail](#gettail)|목록의 끝에 있는 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetTailPosition](#gettailposition)|목록의 끝 위치를 가져오는이 메서드를 호출 합니다.|  
|[CAtlList::InsertAfter](#insertafter)|지정된 된 위치 다음 목록에 새 요소를 삽입 하려면이 메서드를 호출 합니다.|  
|[CAtlList::InsertBefore](#insertbefore)|지정된 된 위치 앞부분의 목록에 새 요소를 삽입 하려면이 메서드를 호출 합니다.|  
|[CAtlList::IsEmpty](#isempty)|목록 비어 있는지 확인 하려면이 메서드를 호출 합니다.|  
|[CAtlList::MoveToHead](#movetohead)|목록 헤드에 지정된 된 요소를 이동 하려면이 메서드를 호출 합니다.|  
|[CAtlList::MoveToTail](#movetotail)|목록의 끝에 지정된 된 요소를 이동 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveAll](#removeall)|목록에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveAt](#removeat)|목록에서 단일 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveHead](#removehead)|목록의 처음 부분에 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|값을 반환 하지 않고 목록 헤드에 있는 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveTail](#removetail)|목록의 끝에 있는 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|값을 반환 하지 않고 목록의 끝에 있는 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::SetAt](#setat)|목록에서 지정된 된 위치에 요소 값을 설정 하려면이 메서드를 호출 합니다.|  
|[CAtlList::SwapElements](#swapelements)|목록에서 요소를 교체 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 `CAtlList` 클래스는 순차적으로 또는 값별로 액세스할 수 있는 고유 하지 않은 개체의 목록을 정렬 하는 지원 합니다. `CAtlList`이중 연결된 목록 처럼 동작합니다. 앞면과 뒷면으로 각 목록에 및 새 요소 (또는 경우에 따라 목록) 목록의 한쪽 끝에 추가 또는 앞 이나 뒤 특정 요소를 삽입 될 수 있습니다.  
  
 대부분의 `CAtlList` 메서드 위치 값을 사용 합니다. 이 값은 없는 요소를 저장 된 및 계산 하거나 안 직접 예측 실제 메모리 위치를 참조 하는 메서드에서 사용 됩니다. 액세스 해야 하는 경우는  *n* th 요소는 메서드 목록에 [CAtlList::FindIndex](#findindex) 지정된 된 인덱스에 대 한 해당 위치 값을 반환 합니다. 메서드 [CAtlList::GetNext](#getnext) 및 [CAtlList::GetPrev](#getprev) 목록에 개체를 반복 하는 데 될 수 있습니다.  
  
 ATL과 사용할 수 있는 컬렉션 클래스에 대 한 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="addhead"></a>CAtlList::AddHead  
 목록 헤드에 요소를 추가 하려면이 메서드를 호출 합니다.  
  
```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```  
  
### <a name="parameters"></a>매개 변수  
 `element`  
 새 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 추가 된 요소의 위치를 반환합니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전을 사용 하는 경우 빈 요소가 해당 복사 생성자가 아닌 기본 생성자를 사용 하 여 만들어집니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]  
  
##  <a name="addheadlist"></a>CAtlList::AddHeadList  
 목록 헤드에 기존 목록에 추가 하려면이 메서드를 호출 합니다.  
  
```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>매개 변수  
 `plNew`  
 추가할 목록입니다.  
  
### <a name="remarks"></a>설명  
 목록에서 가리키는 `plNew` 기존 목록의 시작 부분에 삽입 됩니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `plNew` NULL과 같습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]  
  
##  <a name="addtail"></a>CAtlList::AddTail  
 이 목록의 꼬리에 요소를 추가 하려면이 메서드를 호출 합니다.  
  
```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```  
  
### <a name="parameters"></a>매개 변수  
 `element`  
 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 추가 된 요소의 위치를 반환합니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전을 사용 하는 경우 빈 요소가 해당 복사 생성자가 아닌 기본 생성자를 사용 하 여 만들어집니다. 요소는 목록 끝에 추가 됩니다 하 고 있으므로 비상 이제 됩니다. 이 메서드는 빈 목록으로 사용할 수 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]  
  
##  <a name="addtaillist"></a>CAtlList::AddTailList  
 이 목록의 꼬리에 기존 목록에 추가 하려면이 메서드를 호출 합니다.  
  
```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>매개 변수  
 `plNew`  
 추가할 목록입니다.  
  
### <a name="remarks"></a>설명  
 목록에서 가리키는 `plNew` 뒤에 삽입 됩니다 마지막 요소 (있는 경우)에 있는 목록 개체. 마지막 요소는 `plNew` 목록 꼬리를 따라서 됩니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다 *plNew* NULL과 같습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]  
  
##  <a name="assertvalid"></a>CAtlList::AssertValid  
 유효한 목록을 확인 하려면이 메서드를 호출 합니다.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류가 있는 목록 개체가 유효 하지 않을 경우 발생 합니다. 유효 하려면 빈 목록 헤드와 NULL 가리키는 비상 있고 비어 있지 않은 목록 헤드와 유효한 주소를 가리키는 꼬리 있어야 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]  
  
##  <a name="catllist"></a>CAtlList::CAtlList  
 생성자입니다.  
  
```
CAtlList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBlockSize`  
 블록 크기입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 생성자는 `CAtlList` 개체입니다. 블록 크기는 새 요소가 필요한 경우 할당 된 메모리의 업무량을 측정 합니다. 블록 크기는 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 하 여 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]  
  
##  <a name="dtor"></a>CAtlList:: ~ CAtlList  
 소멸자입니다.  
  
```
~CAtlList() throw();
```  
  
### <a name="remarks"></a>설명  
 에 대 한 호출을 포함 하 여 할당 된 모든 리소스를 해제 [CAtlList::RemoveAll](#removeall) 목록에서 모든 요소를 제거 합니다.  
  
 목록에 대 한 호출 후 여전히 일부 요소를 포함 하는 경우 디버그 빌드에 어설션 오류가 발생 합니다 `RemoveAll`합니다.  
  
##  <a name="find"></a>CAtlList::Find  
 지정 된 요소의 목록을 검색 하려면이 메서드를 호출 합니다.  
  
```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `element`  
 목록에서 찾을 요소입니다.  
  
 `posStartAfter`  
 검색 시작 위치입니다. 지정은 값이 없으면 head 요소와 검색을 시작 합니다.  
  
### <a name="return-value"></a>반환 값  
 요소의 위치 값을 반환 발견 하 고, 그렇지 않으면 NULL을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 있는 목록 개체가 유효 하지 않을 경우 또는 경우 어설션 오류가 발생 합니다는 `posStartAfter` 값 범위를 벗어났습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]  
  
##  <a name="findindex"></a>CAtlList::FindIndex  
 인덱스 값이 지정 된 요소의 위치를 가져오려면이 메서드를 호출 합니다.  
  
```
POSITION FindIndex(size_t iElement) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `iElement`  
 요청된 된 목록 요소의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 하는 경우 해당 위치 값 또는 NULL을 반환 `iElement` 범위를 벗어났습니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 반환에 액세스할 수 있도록 위치 지정 된 인덱스 값에 해당 하는  *n* th 요소는 목록에 있습니다.  
  
 디버그 빌드에 어설션 오류가 있는 목록 개체가 유효 하지 않을 경우 발생 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]  
  
##  <a name="getat"></a>CAtlList::GetAt  
 목록에서 지정된 된 위치에 있는 요소를 반환 하려면이 메서드를 호출 합니다.  
  
```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 특정 요소를 지정 하는 위치 값입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조 또는의 요소의 복사본입니다.  
  
### <a name="remarks"></a>설명  
 목록이 **const**, `GetAt` 요소의 복사본을 반환 합니다. 메서드를 대입문의 오른쪽에만 사용할 수 있으며 목록을 수정 되지 않도록에서 보호 합니다.  
  
 목록 없으면 **const**, `GetAt` 요소에 대 한 참조를 반환 합니다. 이 통해 대입문의 어느 쪽에 사용할 메서드가 목록 항목을 수정할 수 있습니다.  
  
 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `pos` NULL과 같습니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::FindIndex](#findindex)합니다.  
  
##  <a name="getcount"></a>CAtlList::GetCount  
 목록에서 개체의 수를 반환 하려면이 메서드를 호출 합니다.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 목록에 있는 요소 수를 반환합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::Find](#find)합니다.  
  
##  <a name="gethead"></a>CAtlList::GetHead  
 목록의 처음 부분에 요소를 반환 하려면이 메서드를 호출 합니다.  
  
```
E& GetHead() throw();
const E& GetHead() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조 또는 목록의 처음 부분에 요소의 복사본을 반환합니다.  
  
### <a name="remarks"></a>설명  
 목록이 **const**, `GetHead` 목록 헤드에 있는 요소의 복사본을 반환 합니다. 메서드를 대입문의 오른쪽에만 사용할 수 있으며 목록을 수정 되지 않도록에서 보호 합니다.  
  
 목록 없으면 **const**, `GetHead` 목록 헤드에 있는 요소에 대 한 참조를 반환 합니다. 이 통해 대입문의 어느 쪽에 사용할 메서드가 목록 항목을 수정할 수 있습니다.  
  
 디버그 빌드에 어설션 오류는 NULL로 목록의 시작 하는 경우 발생 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::AddHead](#addhead)합니다.  
  
##  <a name="getheadposition"></a>CAtlList::GetHeadPosition  
 목록의 시작 위치를 가져오는이 메서드를 호출 합니다.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 목록의 처음 부분에 요소에 해당 하는 위치 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 목록이 비어 있으면 반환 되는 값은 NULL입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]  
  
##  <a name="getnext"></a>CAtlList::GetNext  
 목록에서 다음 요소를 반환 하려면이 메서드를 호출 합니다.  
  
```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 이전 호출에서 반환 되는 위치 값 `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), 또는 기타 `CAtlList` 메서드.  
  
### <a name="return-value"></a>반환 값  
 목록이 **const**, `GetNext` 목록의 다음 요소의 복사본을 반환 합니다. 메서드를 대입문의 오른쪽에만 사용할 수 있으며 목록을 수정 되지 않도록에서 보호 합니다.  
  
 목록 없으면 **const**, `GetNext` 목록의 다음 요소에 대 한 참조를 반환 합니다. 이 통해 대입문의 어느 쪽에 사용할 메서드가 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 위치 카운터 `pos`, 더 많은 요소가 있는 경우에 NULL 또는 목록에서 다음 요소를 가리키도록 업데이트 됩니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `pos` NULL과 같습니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::GetHeadPosition](#getheadposition)합니다.  
  
##  <a name="getprev"></a>CAtlList::GetPrev  
 목록에서 이전 요소를 반환 하려면이 메서드를 호출 합니다.  
  
```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 이전 호출에서 반환 되는 위치 값 `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), 또는 기타 `CAtlList` 메서드.  
  
### <a name="return-value"></a>반환 값  
 목록이 **const**, `GetPrev` 목록의 요소의 복사본을 반환 합니다. 메서드를 대입문의 오른쪽에만 사용할 수 있으며 목록을 수정 되지 않도록에서 보호 합니다.  
  
 목록 없으면 **const**, `GetPrev` 목록의 요소에 대 한 참조를 반환 합니다. 이 통해 대입문의 어느 쪽에 사용할 메서드가 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 위치 카운터 `pos`, 목록에서 이전 요소를 가리키거나 더 이상 요소가 없는 경우 NULL 하도록 업데이트 됩니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `pos` NULL과 같습니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::GetTailPosition](#gettailposition)합니다.  
  
##  <a name="gettail"></a>CAtlList::GetTail  
 목록의 끝에 있는 요소를 반환 하려면이 메서드를 호출 합니다.  
  
```
E& GetTail() throw();
const E& GetTail() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조 또는 목록의 끝에 있는 요소의 복사본을 반환합니다.  
  
### <a name="remarks"></a>설명  
 목록이 **const**, `GetTail` 목록 헤드에 있는 요소의 복사본을 반환 합니다. 메서드를 대입문의 오른쪽에만 사용할 수 있으며 목록을 수정 되지 않도록에서 보호 합니다.  
  
 목록 없으면 **const**, `GetTail` 목록 헤드에 있는 요소에 대 한 참조를 반환 합니다. 이 통해 대입문의 어느 쪽에 사용할 메서드가 목록 항목을 수정할 수 있습니다.  
  
 디버그 빌드에서 목록 꼬리 NULL 가리키는 어설션 오류가 발생 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::AddTail](#addtail)합니다.  
  
##  <a name="gettailposition"></a>CAtlList::GetTailPosition  
 목록의 끝 위치를 가져오는이 메서드를 호출 합니다.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 목록의 끝에 있는 요소에 해당 하는 위치 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 목록이 비어 있으면 반환 되는 값은 NULL입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]  
  
##  <a name="inargtype"></a>CAtlList::INARGTYPE  
 요소는 입력 인수로 전달 될 때 사용 되는 형식입니다.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertafter"></a>CAtlList::InsertAfter  
 지정된 된 위치 다음 목록에 새 요소를 삽입 하려면이 메서드를 호출 합니다.  
  
```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 새 요소가 삽입 될 위치 값입니다.  
  
 `element`  
 삽입할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 새 요소의 위치 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에서 목록 잘못 삽입이 실패 하는 경우 또는 꼬리 뒤 요소를 삽입 하려고 시도 하는 경우 어설션 오류가 발생 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]  
  
##  <a name="insertbefore"></a>CAtlList::InsertBefore  
 지정된 된 위치 앞부분의 목록에 새 요소를 삽입 하려면이 메서드를 호출 합니다.  
  
```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 새 요소가 목록 위치 값이 앞에 삽입 됩니다.  
  
 `element`  
 삽입할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 새 요소의 위치 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에서 목록 잘못 삽입이 실패 하는 경우 또는 헤드 앞 요소를 삽입 하려고 시도 하는 경우 어설션 오류가 발생 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]  
  
##  <a name="isempty"></a>CAtlList::IsEmpty  
 목록 비어 있는지 확인 하려면이 메서드를 호출 합니다.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 목록에 없는 객체, 그렇지 않으면 false 있으면 true를 반환 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]  
  
##  <a name="movetohead"></a>CAtlList::MoveToHead  
 목록 헤드에 지정된 된 요소를 이동 하려면이 메서드를 호출 합니다.  
  
```
void MoveToHead(POSITION pos) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 이동 하는 요소의 위치 값입니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 요소 목록 헤드의 현재 위치에서 이동 합니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `pos` NULL과 같습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]  
  
##  <a name="movetotail"></a>CAtlList::MoveToTail  
 목록의 끝에 지정된 된 요소를 이동 하려면이 메서드를 호출 합니다.  
  
```
void MoveToTail(POSITION pos) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 이동 하는 요소의 위치 값입니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 요소는 현재 위치에서 목록의 끝으로 이동 됩니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `pos` NULL과 같습니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::MoveToHead](#movetohead)합니다.  
  
##  <a name="removeall"></a>CAtlList::RemoveAll  
 목록에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 목록에서 모든 요소를 제거 하 고 할당 된 메모리를 해제 합니다. 디버그 빌드에는 ATLASSERT은 요소를 모두 삭제 되지 않습니다 또는 목록 구조가 손상 될 경우 발생 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::IsEmpty](#isempty)합니다.  
  
##  <a name="removeat"></a>CAtlList::RemoveAt  
 목록에서 단일 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 제거할 요소의 위치 값입니다.  
  
### <a name="remarks"></a>설명  
 참조 하는 요소의 `pos` 제거 되 면 메모리를 해제 하 고 있습니다. 사용 하는 것이 좋습니다 `RemoveAt` h e a d 또는 목록의 끝을 제거 하려면.  
  
 디버그 빌드에 어설션 오류는 목록에 유효 하지 않을 경우 또는 요소를 제거 하면 목록이 해당 메모리에 액세스 하는 목록 구조의 일부가 아닌 경우 발생 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]  
  
##  <a name="removehead"></a>CAtlList::RemoveHead  
 목록의 처음 부분에 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
E RemoveHead();
```  
  
### <a name="return-value"></a>반환 값  
 목록의 처음 부분에 요소를 반환합니다.  
  
### <a name="remarks"></a>설명  
 메모리를 해제 및 head 요소는 목록에서 삭제 됩니다. 요소의 복사본 반환 됩니다. 디버그 빌드에 어설션 오류는 목록이 비어 있는 경우 발생 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]  
  
##  <a name="removeheadnoreturn"></a>CAtlList::RemoveHeadNoReturn  
 값을 반환 하지 않고 목록 헤드에 있는 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveHeadNoReturn() throw();
```  
  
### <a name="remarks"></a>설명  
 메모리를 해제 및 head 요소는 목록에서 삭제 됩니다. 디버그 빌드에 어설션 오류는 목록이 비어 있는 경우 발생 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::IsEmpty](#isempty)합니다.  
  
##  <a name="removetail"></a>CAtlList::RemoveTail  
 목록의 끝에 있는 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
E RemoveTail();
```  
  
### <a name="return-value"></a>반환 값  
 목록의 끝에 요소를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 메모리를 해제 및 비상 요소 목록에서 삭제 됩니다. 요소의 복사본 반환 됩니다. 디버그 빌드에 어설션 오류는 목록이 비어 있는 경우 발생 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]  
  
##  <a name="removetailnoreturn"></a>CAtlList::RemoveTailNoReturn  
 값을 반환 하지 않고 목록의 끝에 있는 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveTailNoReturn() throw();
```  
  
### <a name="remarks"></a>설명  
 메모리를 해제 및 비상 요소 목록에서 삭제 됩니다. 디버그 빌드에 어설션 오류는 목록이 비어 있는 경우 발생 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlList::IsEmpty](#isempty)합니다.  
  
##  <a name="setat"></a>CAtlList::SetAt  
 목록에서 지정된 된 위치에 요소 값을 설정 하려면이 메서드를 호출 합니다.  
  
```
void SetAt(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 변경 하려면 요소에 해당 하는 위치 값입니다.  
  
 `element`  
 새 요소 값입니다.  
  
### <a name="remarks"></a>설명  
 기존 값을 대체 `element`합니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `pos` NULL과 같습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]  
  
##  <a name="swapelements"></a>CAtlList::SwapElements  
 목록에서 요소를 교체 하려면이 메서드를 호출 합니다.  
  
```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pos1*  
 첫 번째 위치 값입니다.  
  
 *pos2*  
 두 번째 위치 값입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 두 위치에서 요소를 바꿉니다. 디버그 빌드에 어설션 오류는 어느 위치 값이 NULL로 발생 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CList 클래스](../../mfc/reference/clist-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
