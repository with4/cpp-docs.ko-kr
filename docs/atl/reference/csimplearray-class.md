---
title: "CSimpleArray 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e261f95a375a2edda1d543a36b605d23fc718b99
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearray-class"></a>CSimpleArray 클래스
이 클래스는 간단한 배열 관리 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>  
class CSimpleArray
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 배열에 저장할 데이터의 형식입니다.  
  
 `TEqual`  
 형식의 요소에 대 한 같음 테스트를 정의 하는 특성 개체 `T`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleArray::CSimpleArray](#csimplearray)|단순 배열에 대 한 생성자입니다.|  
|[CSimpleArray:: ~ CSimpleArray](#dtor)|단순 배열에 대 한 소멸자가 있습니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleArray::Add](#add)|배열에 새 요소를 추가 합니다.|  
|[CSimpleArray::Find](#find)|배열의 요소를 찾습니다.|  
|[CSimpleArray::GetData](#getdata)|배열에 저장 된 데이터에 대 한 포인터를 반환 합니다.|  
|[CSimpleArray::GetSize](#getsize)|배열에 저장 된 요소의 수를 반환 합니다.|  
|[CSimpleArray::Remove](#remove)|배열에서 지정된 된 요소를 제거합니다.|  
|[CSimpleArray::RemoveAll](#removeall)|배열의 모든 요소를 제거합니다.|  
|[CSimpleArray::RemoveAt](#removeat)|배열에서 지정된 된 요소를 제거합니다.|  
|[CSimpleArray::SetAtIndex](#setatindex)|배열에서 지정된 된 요소를 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleArray::operator\[\]](#operator_at)|배열에서 요소를 검색합니다.|  
|[CSimpleArray::operator =](#operator_eq)|대입 연산자입니다.|  

  
## <a name="remarks"></a>주의  
 `CSimpleArray`만들고 지정 된 형식의 간단한 배열 관리 하기 위한 메서드를 제공 `T`합니다.  
  
 매개 변수 `TEqual` 형식의 두 가지 요소에 대 한 같음 함수를 정의 하는 수단을 제공 `T`합니다. 클래스를 만들어 비슷합니다 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), 모든 지정 된 배열에 대 한 같음 테스트의 동작을 변경 하는 것이 불가능 합니다. 예를 들어 포인터의 배열을 처리할 때 포인터 참조 값에 따라으로 같음을 정의에 유용할 수 있습니다. 기본 구현에서는 **operator=()**합니다.  
  
 둘 다 `CSimpleArray` 및 [CSimpleMap](../../atl/reference/csimplemap-class.md) 는 적은 수의 요소에 대 한 설계 되었습니다. [CAtlArray](../../atl/reference/catlarray-class.md) 및 [CAtlMap](../../atl/reference/catlmap-class.md) 배열 많은 수의 요소를 포함 하는 경우에 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpcoll.h  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&86;](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleArray::Add  
 배열에 새 요소를 추가 합니다.  
  
```
BOOL Add(const T& t);
```  
  
### <a name="parameters"></a>매개 변수  
 *t*  
 배열에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 성공적으로에 추가 됩니다 FALSE 배열, 그렇지 않으면 TRUE를 반환 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&87;](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]  
  
##  <a name="csimplearray"></a>CSimpleArray::CSimpleArray  
 Array 개체에 대 한 생성자입니다.  
  
```
CSimpleArray(const CSimpleArray<T, TEqual>& src);  
CSimpleArray();
```     
  
### <a name="parameters"></a>매개 변수  
 *src*  
 기존 `CSimpleArray` 개체입니다.  
  
### <a name="remarks"></a>주의  
 비어 있는 새를 만드는 데이터 멤버를 초기화 `CSimpleArray` 개체나 기존 사본을 `CSimpleArray` 개체입니다.  
  
##  <a name="dtor"></a>CSimpleArray:: ~ CSimpleArray  
 소멸자입니다.  
  
```
~CSimpleArray();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="find"></a>CSimpleArray::Find  
 배열의 요소를 찾습니다.  
  
```
int Find(const T& t) const;
```  
  
### <a name="parameters"></a>매개 변수  
 *t*  
 검색할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 없는 경우에 찾은 요소의 또는-1 인덱스를 반환 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&88;](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]  
  
##  <a name="getdata"></a>CSimpleArray::GetData  
 배열에 저장 된 데이터에 대 한 포인터를 반환 합니다.  
  
```
T* GetData() const;
```  
  
### <a name="return-value"></a>반환 값  
 배열에 있는 데이터에 대 한 포인터를 반환합니다.  
  
##  <a name="getsize"></a>CSimpleArray::GetSize  
 배열에 저장 된 요소의 수를 반환 합니다.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>반환 값  
 배열에 저장 된 요소의 수를 반환 합니다.  
  
##  <a name="operator_at"></a>CSimpleArray::operator\[\]  
 배열에서 요소를 검색합니다.  
  
```
T& operator[](int nindex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 요소의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 참조 하는 배열의 요소를 반환 `nIndex`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&89;](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]  
  
##  <a name="operator_eq"></a>CSimpleArray::operator =  
 대입 연산자입니다.  
  
```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```  
  
### <a name="parameters"></a>매개 변수  
 *src*  
 복사할 배열입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트에 대 한 포인터를 반환 `CSimpleArray` 개체입니다.  
  
### <a name="remarks"></a>주의  
 요소를 모두 복사는 `CSimpleArray` 개체에서 참조 *src* 는 현재 배열의 개체에 기존의 모든 데이터를 대체 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&90;](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]  
  
##  <a name="remove"></a>CSimpleArray::Remove  
 배열에서 지정된 된 요소를 제거합니다.  
  
```
BOOL Remove(const T& t);
```  
  
### <a name="parameters"></a>매개 변수  
 *t*  
 배열에서 제거할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 인지 발견 및 제거, FALSE 그렇지 않으면 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 요소를 제거 하는 경우 배열의 나머지 요소 빈 공간을 채우기 위해 매겨집니다.  
  
##  <a name="removeall"></a>CSimpleArray::RemoveAll  
 배열의 모든 요소를 제거합니다.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>주의  
 현재 배열에 저장 된 모든 요소를 제거 합니다.  
  
##  <a name="removeat"></a>CSimpleArray::RemoveAt  
 배열에서 지정된 된 요소를 제거합니다.  
  
```
BOOL RemoveAtint nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 요소를 가리키는 제거할 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 해당 요소가 닫힌 인덱스가 유효 하지 않은 경우 FALSE로 설정 제거 하는 경우 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 요소를 제거 하는 경우 배열의 나머지 요소 빈 공간을 채우기 위해 매겨집니다.  
  
##  <a name="setatindex"></a>CSimpleArray::SetAtIndex  
 배열에서 지정된 된 요소를 설정 합니다.  
  
```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스를 변경할 요소입니다.  
  
 *t*  
 지정된 요소에 할당할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 경우 TRUE를 반환 성공적이 고, FALSE 인덱스가 잘못 되었습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

