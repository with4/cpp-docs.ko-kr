---
title: CTypedPtrList 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afb32a662c538526c4fe26f6abf46e56a42de728
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374590"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList 클래스
클래스 `CPtrList`의 개체에 대한 형식 안전 "래퍼"를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>매개 변수  
 `BASE_CLASS`  
 형식화 된 포인터 목록 클래스;의 기본 클래스 포인터 목록 클래스 여야 합니다 ( `CObList` 또는 `CPtrList`).  
  
 `TYPE`  
 기본 클래스 목록에 저장 된 요소의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|(새 헤드는) 목록 헤드에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|  
|[CTypedPtrList::AddTail](#addtail)|(새 비상은) 목록의 끝에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|  
|[CTypedPtrList::GetAt](#getat)|지정된 된 위치에 요소를 가져옵니다.|  
|[CTypedPtrList::GetHead](#gethead)|목록 (비어 있을 수 없습니다)의 head 요소를 반환 합니다.|  
|[CTypedPtrList::GetNext](#getnext)|반복 하는 데 다음 요소를 가져옵니다.|  
|[CTypedPtrList::GetPrev](#getprev)|반복 하는 데 이전 요소를 가져옵니다.|  
|[CTypedPtrList::GetTail](#gettail)|(비어 있을 수 없습니다) 목록의 꼬리 요소를 반환 합니다.|  
|[CTypedPtrList::RemoveHead](#removehead)|목록의 시작에서 요소를 제거 합니다.|  
|[CTypedPtrList::RemoveTail](#removetail)|목록 꼬리에서 요소를 제거 합니다.|  
|[CTypedPtrList::SetAt](#setat)|지정된 된 위치에 요소를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 사용 하는 경우 `CTypedPtrList` 대신 `CObList` 또는 `CPtrList`, c + + 형식 검사 기능에 일치 하지 않는 포인터 형식으로 인 한 오류를 제거 하는 데 도움이 됩니다.  
  
 또한는 `CTypedPtrList` 래퍼를 사용한 경우 필요할 수 캐스팅의 많은 수행 `CObList` 또는 `CPtrList`합니다.  
  
 때문에 모든 `CTypedPtrList` 함수는 인라인, 크기 또는 코드의 속도이 템플릿을 사용 하 여 크게 적용 되지 않습니다.  
  
 목록에서 파생 된 `CObList` 를 serialize 할 수 있지만 파생 된 `CPtrList` 수 없습니다.  
  
 `CTypedPtrList` 개체를 삭제하거나 해당 요소를 제거할 경우 참조하는 엔터티가 아니라 포인터만 제거됩니다.  
  
 사용 하 여 대 한 자세한 내용은 `CTypedPtrList`, 문서를 참조 [컬렉션](../../mfc/collections.md) 및 [템플릿 기반 클래스](../../mfc/template-based-classes.md)합니다.  
  
## <a name="example"></a>예제  
 이 예의 인스턴스를 만들고 `CTypedPtrList`, 하나의 개체 추가, 디스크, 목록 또는 그 반대로 serialize 하 고 다음 개체를 삭제 합니다.  
  
 [!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtempl.h  
  
##  <a name="addhead"></a>  CTypedPtrList::AddHead  
 이 멤버 함수를 호출 `BASE_CLASS` **:: AddHead**합니다.  
  
```  
POSITION AddHead(TYPE newElement);  
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 기본 클래스 목록에 저장 된 요소의 형식입니다.  
  
 `newElement`  
 이 목록에 추가할 개체 포인터입니다. A **NULL** 값은 사용할 수 있습니다.  
  
 `BASE_CLASS`  
 형식화 된 포인터 목록 클래스;의 기본 클래스 포인터 목록 클래스 여야 합니다 ( [CObList](../../mfc/reference/coblist-class.md) 또는 [해당 클래스가](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 에 대 한 포인터를 다른 [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) 개체입니다. 요소 `pNewList` 이 목록에 추가 됩니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 버전은 반환 된 **위치** 새로 삽입된 된 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전 목록의 시작 하기 전에 새 요소를 추가 합니다. 두 번째 버전은 다른 목록 헤드 하기 전에 요소를 추가합니다.  
  
##  <a name="addtail"></a>  CTypedPtrList::AddTail  
 이 멤버 함수를 호출 `BASE_CLASS` **:: AddTail**합니다.  
  
```  
POSITION AddTail(TYPE newElement);  
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 기본 클래스 목록에 저장 된 요소의 형식입니다.  
  
 `newElement`  
 이 목록에 추가할 개체 포인터입니다. A **NULL** 값은 사용할 수 있습니다.  
  
 `BASE_CLASS`  
 형식화 된 포인터 목록 클래스;의 기본 클래스 포인터 목록 클래스 여야 합니다 ( [CObList](../../mfc/reference/coblist-class.md) 또는 [해당 클래스가](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 에 대 한 포인터를 다른 [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) 개체입니다. 요소 `pNewList` 이 목록에 추가 됩니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 버전은 반환 된 **위치** 새로 삽입된 된 요소의 값입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전 목록 꼬리 후 새 요소를 추가합니다. 두 번째 버전은 목록 꼬리 후 다른 목록 요소를 추가합니다.  
  
##  <a name="getat"></a>  CTypedPtrList::GetAt  
 형식의 변수 **위치** 목록에 대 한 키입니다.  
  
```  
TYPE& GetAt(POSITION position);  
TYPE GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.  
  
 *위치*  
 A **위치** 이전에서 반환 된 값 `GetHeadPosition` 또는 **찾을** 멤버 함수 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록에 대 한 포인터를 통해 액세스 하는 경우는 **const CTypedPtrList**, 다음 `GetAt` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 *형식*합니다. 이 함수를 대입문의 오른쪽에만 사용할 수 있도록 하며 따라서 수정 되지 않도록에서 목록을 보호 합니다.  
  
 목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 다음 `GetAt` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 인덱스를 동일 하지 않습니다 및 작업할 수 없습니다. 한 **위치** 직접 값입니다. `GetAt` 검색 된 `CObject` 지정된 된 위치와 연결 된 포인터입니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
 이 인라인 함수가 호출 `BASE_CLASS` **:: GetAt**합니다.  
  
##  <a name="gethead"></a>  CTypedPtrList::GetHead  
 이 목록의 헤드 요소를 나타내는 포인터를 가져옵니다.  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록에 대 한 포인터를 통해 액세스 하는 경우는 **const CTypedPtrList**, 다음 `GetHead` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 *형식*합니다. 이 함수를 대입문의 오른쪽에만 사용할 수 있도록 하며 따라서 수정 되지 않도록에서 목록을 보호 합니다.  
  
 목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 다음 `GetHead` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `GetHead`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 포함 되었는지 확인 합니다.  
  
##  <a name="getnext"></a>  CTypedPtrList::GetNext  
 로 식별 되는 목록 요소를 가져옵니다 `rPosition`, 다음 설정 `rPosition` 에 **위치** 목록에서 다음 항목의 값입니다.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 이 목록에 포함 된 요소의 형식을 지정 하는 템플릿 매개 변수  
  
 `rPosition`  
 에 대 한 참조는 **위치** 이전에서 반환 된 값 `GetNext`, `GetHeadPosition`, 또는 기타 멤버 함수 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록에 대 한 포인터를 통해 액세스 하는 경우는 **const CTypedPtrList**, 다음 `GetNext` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 *형식*합니다. 이 함수를 대입문의 오른쪽에만 사용할 수 있도록 하며 따라서 수정 되지 않도록에서 목록을 보호 합니다.  
  
 목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 다음 `GetNext` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 사용할 수 있습니다 `GetNext` 정방향으로 반복 루프를 호출 하 여 초기 위치를 설정 하는 경우에 `GetHeadPosition` 또는 [CPtrList::Find](../../mfc/reference/coblist-class.md#find)합니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
 검색된 된 요소는 목록에서 마지막 다음 새 값의 경우 `rPosition` 로 설정 된 **NULL**합니다.  
  
 반복 하는 동안 요소를 제거 하는 것이 불가능 합니다. 예를 참조 [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)합니다.  
  
##  <a name="getprev"></a>  CTypedPtrList::GetPrev  
 로 식별 되는 목록 요소를 가져옵니다 `rPosition`, 다음 설정 `rPosition` 에 **위치** 목록에서 이전 항목의 값입니다.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 이 목록에 포함 된 요소의 형식을 지정 하는 템플릿 매개 변수  
  
 `rPosition`  
 에 대 한 참조는 **위치** 이전에서 반환 된 값 `GetPrev` 또는 다른 멤버 함수 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록에 대 한 포인터를 통해 액세스 하는 경우는 **const CTypedPtrList**, 다음 `GetPrev` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 *형식*합니다. 이 함수를 대입문의 오른쪽에만 사용할 수 있도록 하며 따라서 수정 되지 않도록에서 목록을 보호 합니다.  
  
 목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 다음 `GetPrev` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 사용할 수 있습니다 `GetPrev` 을 호출 하 여 초기 위치를 설정 하는 경우 역방향 반복 루프에서 `GetTailPosition` 또는 **찾을**합니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
 검색된 된 요소 목록에서 첫 번째 다음의 새 값 이면의 `rPosition` 로 설정 된 **NULL**합니다.  
  
##  <a name="gettail"></a>  CTypedPtrList::GetTail  
 이 목록의 헤드 요소를 나타내는 포인터를 가져옵니다.  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록에 대 한 포인터를 통해 액세스 하는 경우는 **const CTypedPtrList**, 다음 `GetTail` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 *형식*합니다. 이 함수를 대입문의 오른쪽에만 사용할 수 있도록 하며 따라서 수정 되지 않도록에서 목록을 보호 합니다.  
  
 목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 다음 `GetTail` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입 문의 양쪽에 사용 될 함수를 통해 목록 항목을 수정할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `GetTail`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 포함 되었는지 확인 합니다.  
  
##  <a name="removehead"></a>  CTypedPtrList::RemoveHead  
 목록의 시작에서 요소를 제거 하 고 반환 합니다.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록의 처음 부분에 이전에 대 한 포인터입니다. 이 포인터는 템플릿 매개 변수로 지정 된 형식의 *형식*합니다.  
  
### <a name="remarks"></a>설명  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveHead`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 포함 되었는지 확인 합니다.  
  
##  <a name="removetail"></a>  CTypedPtrList::RemoveTail  
 목록 꼬리에서 요소를 제거 하 고 반환 합니다.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 목록의 끝에서 이전에 대 한 포인터입니다. 이 포인터는 템플릿 매개 변수로 지정 된 형식의 *형식*합니다.  
  
### <a name="remarks"></a>설명  
 목록을 호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveTail`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 포함 되었는지 확인 합니다.  
  
##  <a name="setat"></a>  CTypedPtrList::SetAt  
 이 멤버 함수를 호출 `BASE_CLASS` **:: SetAt**합니다.  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 **위치** 설정할 요소입니다.  
  
 *형식*  
 기본 클래스 목록에 저장 된 요소의 형식입니다.  
  
 `newElement`  
 목록에 기록할 개체 포인터입니다.  
  
### <a name="remarks"></a>설명  
 형식의 변수 **위치** 목록에 대 한 키입니다. 인덱스를 동일 하지 않습니다 및 작업할 수 없습니다. 한 **위치** 직접 값입니다. `SetAt` 목록에서 지정된 된 위치에 개체 포인터를 씁니다.  
  
 확인 해야 하면 **위치** 값 목록에서 올바른 위치를 나타냅니다. 유효 하지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.  
  
 설명에 자세한 참조 [CObList::SetAt](../../mfc/reference/coblist-class.md#setat)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [해당 클래스가 클래스](../../mfc/reference/cptrlist-class.md)   
 [CObList 클래스](../../mfc/reference/coblist-class.md)
