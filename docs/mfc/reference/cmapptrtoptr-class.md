---
title: "CMapPtrToPtr 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapPtrToPtr
dev_langs:
- C++
helpviewer_keywords:
- CMapPtrToPtr class
- pointer mapping class
- collection classes, pointer mapping
ms.assetid: 23cbbaec-9d64-48f2-92ae-5e24fa64b926
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b4cb551b9adcd773b7a2c4bd6e7d6fe535e94081
ms.lasthandoff: 02/24/2017

---
# <a name="cmapptrtoptr-class"></a>CMapPtrToPtr 클래스
void 포인터로 키가 지정된 void 포인터 맵을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMapPtrToPtr : public CObject  
```  
  
## <a name="members"></a>멤버  
 멤버 함수는 `CMapPtrToPtr` 클래스의 멤버 함수와 유사 [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)합니다. 이처럼 두 함수가 비슷하므로 `CMapStringToOb` 참조 설명서에서 멤버 함수 관련 사항을 확인할 수 있습니다. `CObject` 포인터를 함수 매개 변수 또는 반환 값으로 볼 때마다 포인터는 `void`로 대체됩니다. 표시 될 때마다는 `CString` 또는 **const** 에 대 한 포인터 `char` 대체에 대 한 포인터를 함수 매개 변수 또는 반환 값으로 `void`합니다.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 예를 들어 위의 코드는  
  
 `BOOL CMapPtrToPtr::Lookup( void* <key>, void*& <rValue> ) const;`  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|이 map의 요소 수를 반환합니다.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|현재 해시 테이블의 요소 수를 결정합니다.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|이 map의 요소 수를 반환합니다.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|첫 번째 요소의 위치를 반환합니다.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|지정된 된 키의 해시 값을 계산합니다.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|해시 테이블을 초기화합니다.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|빈 맵 조건 (요소 없음)에 대해 테스트 합니다.|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void 포인터 키를 기반으로 하는 void 포인터를 조회 합니다. 포인터 값을 가리키는 것 엔터티 하지 비교에 사용 되는 키입니다.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|지정 된 키 값과 연결 된 키에 대 한 참조를 반환 합니다.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|이 맵에서 모든 요소를 제거합니다.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|키가 지정 된 요소를 제거 합니다.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Map에 요소를 삽입합니다. 일치 하는 키가 있을 경우에 기존 요소를 대체 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map에 요소를 삽입-에 대 한 연산자 대체 `SetAt`합니다.|  
  
## <a name="remarks"></a>주의  
 `CMapPtrToPtr`는 `IMPLEMENT_DYNAMIC` 매크로를 통합하여 런타임 형식 액세스와 `CDumpContext` 개체에 대한 덤핑을 지원합니다. 개별 지도 요소 (포인터 값)의 덤프를 해야 하는 경우 덤프 컨텍스트의 수준을 1 이상으로 설정 해야 합니다.  
  
 포인터를 포인터 맵을 serialize 할 수 있습니다.  
  
 `CMapPtrToPtr` 개체를 삭제하거나 해당 요소를 제거할 경우 참조하는 엔터티가 아니라 포인터만 제거됩니다.  
  
 대 한 자세한 내용은 `CMapPtrToPtr`, 문서를 참조 하십시오 [컬렉션](../../mfc/collections.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapPtrToPtr`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcoll.h  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




