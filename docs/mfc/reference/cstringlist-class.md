---
title: CStringList 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
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
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31e13222ccd5ac12768961ff5e93d11e68ecfded
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122717"
---
# <a name="cstringlist-class"></a>CStringList 클래스
`CString` 개체 목록을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CStringList : public CObject  
```  
  
## <a name="members"></a>멤버  
 멤버 함수 `CStringList` 클래스의 멤버 함수와 비슷한 [CObList](../../mfc/reference/coblist-class.md)합니다. 이처럼 두 함수가 비슷하므로 `CObList` 참조 설명서에서 멤버 함수 관련 사항을 확인할 수 있습니다. 볼 때마다는 `CObject` 포인터를 반환 값으로 대체 한 `CString` (하지는 `CString` 포인터). 볼 때마다는 `CObject` 포인터를 함수 매개 변수로 대체는 `LPCTSTR`합니다.  
  
 `CObject*& CObList::GetHead() const;`  
  
 예를 들어 위의 코드는  
  
 `CString& CStringList::GetHead() const;`  
  
 및  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 위의 코드는 다음과 같이 변환됩니다.  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|빈 목록을 생성 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|(새 헤드는) 목록 헤드에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|  
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|(새 비상은) 목록의 끝에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|  
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|포인터 값으로 지정 된 요소의 위치를 가져옵니다.|  
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|0 기반 인덱스에서 지정한 요소의 위치를 가져옵니다.|  
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|지정된 된 위치에 요소를 가져옵니다.|  
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|이 목록의 요소 수를 반환합니다.|  
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|목록 (비어 있을 수 없습니다)의 head 요소를 반환 합니다.|  
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|목록 헤드 요소의 위치를 반환합니다.|  
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|반복 하는 데 다음 요소를 가져옵니다.|  
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|반복 하는 데 이전 요소를 가져옵니다.|  
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|이 목록의 요소 수를 반환합니다.|  
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|(비어 있을 수 없습니다) 목록의 꼬리 요소를 반환 합니다.|  
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|목록의 꼬리 요소의 위치를 반환합니다.|  
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|지정된 된 위치 뒤 새 요소를 삽입합니다.|  
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|지정된 된 위치 앞에 새 요소를 삽입합니다.|  
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|빈 목록 조건 (요소 없음)에 대해 테스트 합니다.|  
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|이 목록에서 모든 요소를 제거합니다.|  
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|위치에 지정 된이 목록에서 요소를 제거 합니다.|  
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|목록의 시작에서 요소를 제거 합니다.|  
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|목록 꼬리에서 요소를 제거 합니다.|  
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|지정된 된 위치에 요소를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 모든 비교는 문자열의 주소 대신 문자열의 문자를 비교할 이므로 값으로 수행 됩니다.  
  
 `CStringList` serialization 및 요소 덤프를 지원 하기 위해 IMPLEMENT_SERIAL 매크로 통합 합니다. 목록을 `CString` 개체는 오버 로드 된 삽입 연산자 또는으로 보관 파일로 저장 됩니다는 `Serialize` 멤버 함수를 각각 `CString` 요소가 차례로 serialize 됩니다.  
  
 개인의 덤프 해야 할 경우 `CString` 요소를 1 이상으로 덤프 컨텍스트 깊이 설정 해야 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CStringList`, 문서를 참조 [컬렉션](../../mfc/collections.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcoll.h  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



