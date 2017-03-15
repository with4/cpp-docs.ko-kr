---
title: "CAtlArray 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlArray
- ATL.CAtlArray
- CAtlArray
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 21
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
ms.openlocfilehash: 5fe987e428fc0dcf3e40bfb16aa26bcb90339aff
ms.lasthandoff: 02/24/2017

---
# <a name="catlarray-class"></a>CAtlArray 클래스
이 클래스는 배열 개체를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```  
  
#### <a name="parameters"></a>매개 변수  
 *E*  
 배열에 저장할 데이터의 형식입니다.  
  
 *ETraits*  
 요소 이동 하거나 복사 하는 데 사용 되는 코드입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[추가](#add)|Array 개체에 요소를 추가 하려면이 메서드를 호출 합니다.|  
|[추가](#append)|한 배열의 내용을 다른 끝에 추가 하려면이 메서드를 호출 합니다.|  
|[AssertValid](#assertvalid)|Array 개체에 유효한 지 확인 하려면이 메서드를 호출 합니다.|  
|[CAtlArray](#catlarray)|생성자입니다.|  
|[~ CAtlArray](#dtor)|소멸자입니다.|  
|[복사](#copy)|다른 한 배열의 요소를 복사 하려면이 메서드를 호출 합니다.|  
|[FreeExtra](#freeextra)|배열에서 빈 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[GetAt](#getat)|Array 개체에서 단일 요소를 검색 하려면이 메서드를 호출 합니다.|  
|[GetCount](#getcount)|배열에 저장 된 요소의 수를 반환 하려면이 메서드를 호출 합니다.|  
|[GetData](#getdata)|배열의 첫 번째 요소에 대 한 포인터를 반환 하려면이 메서드를 호출 합니다.|  
|[InsertArrayAt](#insertarrayat)|에 다른 배열 삽입 하려면이 메서드를 호출 합니다.|  
|[InsertAt](#insertat)|Array 개체에 새 요소 (또는 여러 개 요소)를 삽입 하려면이 메서드를 호출 합니다.|  
|[IsEmpty](#isempty)|배열이 비어 있는 경우에 테스트 하려면이 메서드를 호출 합니다.|  
|[RemoveAll](#removeall)|Array 개체에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[RemoveAt](#removeat)|배열에서 하나 이상의 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[SetAt](#setat)|배열 개체에서 요소의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[SetAtGrow](#setatgrow)|필요에 따라 배열을 확장 배열 개체에서 요소의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[SetCount](#setcount)|배열 개체의 크기를 설정 하려면이 메서드를 호출 합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator&#91;&#93;](#operator_at)|배열의 요소에 대 한 참조를 반환 하도록이 연산자를 호출 합니다.|  

  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|배열에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.|  
|[OUTARGTYPE](#outargtype)|배열에서 요소를 검색에 사용할 데이터 형식입니다.|  
  
## <a name="remarks"></a>주의  
 **CAtlArray** 만들고 사용자 정의 형식 요소의 배열 관리 하기 위한 메서드를 제공 합니다. 표준 C 배열과 유사 하지만 **CAtlArray** 개체 수 동적으로 축소 하 고 필요에 따라 증가 합니다. 배열 인덱스는 항상 위치 0에서 시작 하 고 상한 수정 하거나 새 요소가 추가 확장 하도록 허용 수입니다.  
  
 적은 수의 요소를 ATL 클래스와 배열에 대 한 [CSimpleArray](../../atl/reference/csimplearray-class.md) 사용할 수 있습니다.  
  
 **CAtlArray** 은 MFC의 밀접 한 관련이 **CArray** 클래스 및 serialization 지원 하지 않는 상태 라도 MFC 프로젝트에서 작동 합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="a-nameadda--catlarrayadd"></a><a name="add"></a>CAtlArray::Add  
 Array 개체에 요소를 추가 하려면이 메서드를 호출 합니다.  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>매개 변수  
 `element`  
 배열에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 요소의 인덱스를 반환합니다.  
  
### <a name="remarks"></a>주의  
 새 요소가 배열의 끝에 추가 됩니다. 요소가 없는 빈 요소 추가 됩니다; 제공 된 경우 즉, 실제 요소를 추가한 것 처럼 배열의 크기가 증가 되었습니다. 작업이 실패 하는 경우 [AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7) E_OUTOFMEMORY 인수를 사용 하 여 호출 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&1;](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="a-nameappenda--catlarrayappend"></a><a name="append"></a>CAtlArray::Append  
 한 배열의 내용을 다른 끝에 추가 하려면이 메서드를 호출 합니다.  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `aSrc`  
 추가할 배열입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 첫 번째 요소의 인덱스를 반환합니다.  
  
### <a name="remarks"></a>주의  
 제공 된 배열에 있는 요소는 기존 배열의 끝에 추가 됩니다. 필요한 경우 새 요소를 수용 하기 위해 메모리를 할당 됩니다.  
  
 배열에는 동일한 형식 이어야 하며 배열 자체에 추가할 수 없는.  
  
 디버그 빌드에서 ATLASSERT 발생 합니다는 `CAtlArray` 인수가 유효한 배열 아닌 경우 `aSrc` 동일한 개체를 참조 합니다. 릴리스 빌드에 잘못 된 인수는 예기치 않은 동작이 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&2;](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="a-nameassertvalida--catlarrayassertvalid"></a><a name="assertvalid"></a>CAtlArray::AssertValid  
 Array 개체에 유효한 지 확인 하려면이 메서드를 호출 합니다.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>주의  
 Array 개체 올바르지 `ATLASSERT` 어설션을 발생 시킵니다. 이 메서드는 _DEBUG이 정의 하는 경우에 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&3;](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="a-namecatlarraya--catlarraycatlarray"></a><a name="catlarray"></a>CAtlArray::CAtlArray  
 생성자입니다.  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>주의  
 배열 개체를 초기화합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&4;](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="a-namedtora--catlarraycatlarray"></a><a name="dtor"></a>CAtlArray:: ~ CAtlArray  
 소멸자입니다.  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>주의  
 Array 개체에서 사용 하는 모든 리소스를 해제 합니다.  
  
##  <a name="a-namecopya--catlarraycopy"></a><a name="copy"></a>CAtlArray::Copy  
 다른 한 배열의 요소를 복사 하려면이 메서드를 호출 합니다.  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `aSrc`  
 소스 요소를 배열에 복사입니다.  
  
### <a name="remarks"></a>주의  
 다른 배열의 요소와 한 배열의 요소를 덮어쓰려면이 메서드를 호출 합니다. 필요한 경우 새 요소를 수용 하기 위해 메모리를 할당 됩니다. 자신에 게 배열의 요소를 복사 하는 것이 불가능 합니다.  
  
 배열의 기존 내용이 보존을 사용 하 여 [CAtlArray::Append](#append) 대신 합니다.  
  
 디버그 빌드에서 ATLASSERT 발생 합니다 기존 `CAtlArray` 개체가 유효 하지 않거나 `aSrc` 동일한 개체를 참조 합니다. 릴리스 빌드에 잘못 된 인수는 예기치 않은 동작이 발생할 수 있습니다.  
  
> [!NOTE]
> `CAtlArray::Copy`사용 하 여 만든 요소로 구성 된 배열을 지원 하지 않는 [CAutoPtr](../../atl/reference/cautoptr-class.md) 클래스입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&5;](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="a-namefreeextraa--catlarrayfreeextra"></a><a name="freeextra"></a>CAtlArray::FreeExtra  
 배열에서 빈 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>주의  
 모든 빈 요소가 제거 되지만 크기와 배열 상한 변경 되지 않습니다.  
  
 올바르지 않은 CAtlArray 개체 또는 배열의 최대 크기를 초과 디버그 빌드에서 ATLASSERT이 발생 합니다.  
  
##  <a name="a-namegetata--catlarraygetat"></a><a name="getat"></a>CAtlArray::GetAt  
 Array 개체에서 단일 요소를 검색 하는이 메서드를 호출 합니다.  
  
```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `iElement`  
 반환할 배열 요소의 인덱스 값입니다.  
  
### <a name="return-value"></a>반환 값  
 필요한 배열 요소에 대 한 참조를 반환합니다.  
  
### <a name="remarks"></a>주의  
 디버그 빌드에서 ATLASSERT 발생 합니다 `iElement` 배열의 요소 수를 초과 합니다. 릴리스 빌드에 잘못 된 인수는 예기치 않은 동작이 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&6;](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="a-namegetcounta--catlarraygetcount"></a><a name="getcount"></a>CAtlArray::GetCount  
 배열에 저장 된 요소의 수를 반환 하려면이 메서드를 호출 합니다.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 배열에 저장 된 요소의 수를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 반환 되는 값 배열에 있는 첫 번째 요소 위치 0에 그대로 `GetCount` 항상 1 보다 크면 가장 큰 인덱스입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CAtlArray::GetAt](#getat)합니다.  
  
##  <a name="a-namegetdataa--catlarraygetdata"></a><a name="getdata"></a>CAtlArray::GetData  
 배열의 첫 번째 요소에 대 한 포인터를 반환 하려면이 메서드를 호출 합니다.  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 배열의 첫 번째 요소를 저장 하는 메모리 위치에 대 한 포인터를 반환 합니다. 요소를 사용할 수 없으면 NULL이 반환 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&7;](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="a-nameinargtypea--catlarrayinargtype"></a><a name="inargtype"></a>CAtlArray::INARGTYPE  
 배열에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="a-nameinsertarrayata--catlarrayinsertarrayat"></a><a name="insertarrayat"></a>CAtlArray::InsertArrayAt  
 에 다른 배열 삽입 하려면이 메서드를 호출 합니다.  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>매개 변수  
 `iStart`  
 배열이 삽입할 인덱스입니다.  
  
 `paNew`  
 삽입 될 배열입니다.  
  
### <a name="remarks"></a>주의  
 배열에서 요소 `paNew` 요소에서 시작 하는 배열 개체에 복사 됩니다 `iStart`합니다. 기존 배열 요소는 덮어쓰지 않으려면 이동 됩니다.  
  
 디버그 빌드에서 ATLASSERT 발생 합니다는 `CAtlArray` 개체가 유효 하지 또는 경우에는 `paNew` 포인터가 NULL 또는 잘못 되었습니다.  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt`사용 하 여 만든 요소로 구성 된 배열을 지원 하지 않는 [CAutoPtr](../../atl/reference/cautoptr-class.md) 클래스입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&8;](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="a-nameinsertata--catlarrayinsertat"></a><a name="insertat"></a>CAtlArray::InsertAt  
 Array 개체에 새 요소 (또는 여러 개 요소)를 삽입 하려면이 메서드를 호출 합니다.  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `iElement`  
 요소 또는 요소 삽입 되는 인덱스입니다.  
  
 `element`  
 요소 또는 요소를 삽입할 수의 값입니다.  
  
 `nCount`  
 추가할 요소의 수입니다.  
  
### <a name="remarks"></a>주의  
 인덱스에서 시작 하는 배열에 하나 이상의 요소를 삽입 `iElement`합니다. 기존 요소는 덮어쓰지 않으려면 이동 됩니다.  
  
 디버그 빌드에서 ATLASSERT 발생 합니다는 `CAtlArray` 개체가 유효 하지 않습니다, 요소를 추가할 수는&0; 또는 조합 된 요소 수를 포함 하는 배열에 대 한 너무 큽니다. 정품 빌드에는 잘못 된 매개 변수를 전달 하면 예상치 못한 결과가 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&9;](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="a-nameisemptya--catlarrayisempty"></a><a name="isempty"></a>CAtlArray::IsEmpty  
 배열이 비어 있는 경우에 테스트 하려면이 메서드를 호출 합니다.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 배열이 비어 있으면 false 그렇지 않으면 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 배열의는 요소가 없는 경우 비어 있도록 라고 합니다. 따라서 빈 요소를 포함 하는 배열, 경우에이 비어 있지 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&10;](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="a-nameoperatorata--catlarrayoperator-"></a><a name="operator_at"></a>CAtlArray::operator]  
 배열의 요소에 대 한 참조를 반환 하도록이 연산자를 호출 합니다.  
  
```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `iElement`  
 반환할 배열 요소의 인덱스 값입니다.  
  
### <a name="return-value"></a>반환 값  
 필요한 배열 요소에 대 한 참조를 반환합니다.  
  
### <a name="remarks"></a>주의  
 비슷한 기능을 수행 [CAtlArray::GetAt](#getat)합니다. MFC 클래스와 달리 [CArray](../../mfc/reference/carray-class.md),이 연산자를 대신 사용할 수 없습니다 [CAtlArray::SetAt](#setat)합니다.  
  
 디버그 빌드에서 ATLASSERT 발생 합니다 `iElement` 배열에 있는 요소의 총 수를 초과 합니다. 일반 정품 빌드에 잘못 된 매개 변수 예상치 못한 결과가 발생할 수 있습니다.  
  
##  <a name="a-nameoutargtypea--catlarrayoutargtype"></a><a name="outargtype"></a>CAtlArray::OUTARGTYPE  
 배열에서 요소를 검색에 사용할 데이터 형식입니다.  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="a-nameremovealla--catlarrayremoveall"></a><a name="removeall"></a>CAtlArray::RemoveAll  
 Array 개체에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>주의  
 Array 개체에서 모든 요소를 제거합니다.  
  
 이 메서드를 호출 [CAtlArray::SetCount](#setcount) 배열 크기를 조정 하 고 이후에 할당 된 메모리를 해제 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CAtlArray::IsEmpty](#isempty)합니다.  
  
##  <a name="a-nameremoveata--catlarrayremoveat"></a><a name="removeat"></a>CAtlArray::RemoveAt  
 배열에서 하나 이상의 요소를 제거 하려면이 메서드를 호출 합니다.  
  
```
void RemoveAt(size_t iElement, size_t nCount = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `iElement`  
 제거할 첫 번째 요소의 인덱스입니다.  
  
 `nCount`  
 제거할 요소의 수입니다.  
  
### <a name="remarks"></a>주의  
 배열에서 하나 이상의 요소를 제거합니다. 남아 있는 요소를 아래로 이동 합니다. 상한값은 감소 하지만 메모리에 대 한 호출 될 때까지 비워지지 않고 [CAtlArray::FreeExtra](#freeextra) 이루어집니다.  
  
 디버그 빌드에서 ATLASSERT 발생 합니다는 `CAtlArray` 개체가 올바른지 경우 결합된 된 총 `iElement` 및 `nCount` 배열에 있는 요소의 총 수를 초과 합니다. 일반 정품 빌드에 잘못 된 매개 변수 예상치 못한 결과가 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&11;](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="a-namesetata--catlarraysetat"></a><a name="setat"></a>CAtlArray::SetAt  
 배열 개체에서 요소의 값을 설정 하려면이 메서드를 호출 합니다.  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>매개 변수  
 `iElement`  
 설정할 수 있는 배열 요소를 가리키는 인덱스입니다.  
  
 `element`  
 지정한 요소의 새 값입니다.  
  
### <a name="remarks"></a>주의  
 디버그 빌드에서 ATLASSERT 발생 합니다 `iElement` 배열의 요소 수를 초과 합니다. 일반 정품 빌드에 잘못 된 매개 변수 예상치 못한 결과가 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CAtlArray::GetAt](#getat)합니다.  
  
##  <a name="a-namesetcounta--catlarraysetcount"></a><a name="setcount"></a>CAtlArray::SetCount  
 배열 개체의 크기를 설정 하려면이 메서드를 호출 합니다.  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewSize`  
 필요한 배열의 크기입니다.  
  
 `nGrowBy`  
 확인 하는 데 사용 되는 값 크기의 버퍼를 합니다. -1 값을 이면는 내부적으로 계산 된 값을 사용할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않은 경우 배열 크기가 고, false 성공적으로 크기가 조정 된 경우 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 배열 증가 하거나 크기가 감소 될 수 있습니다. 증가 하는 경우 추가 빈 요소는 배열에 추가 됩니다. 감소 하는 경우 가장 큰 인덱스와 함께 요소 삭제 되 고 메모리를 해제 합니다.  
  
 이 메서드를 사용 하 여 사용 하기 전에 배열의 크기를 설정 합니다. 경우 `SetCount` 를 사용 하지 않으면 요소를 추가 하는 과정-후속 메모리 할당을 수행 하 고-성능이 감소 하 고 메모리를 조각화 됩니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CAtlArray::GetData](#getdata)합니다.  
  
##  <a name="a-namesetatgrowa--catlarraysetatgrow"></a><a name="setatgrow"></a>CAtlArray::SetAtGrow  
 필요에 따라 배열을 확장 배열 개체에서 요소의 값을 설정 하려면이 메서드를 호출 합니다.  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>매개 변수  
 `iElement`  
 설정할 수 있는 배열 요소를 가리키는 인덱스입니다.  
  
 `element`  
 지정한 요소의 새 값입니다.  
  
### <a name="remarks"></a>주의  
 인덱스에서 가리키는 요소의 값을 대체 합니다. 경우 `iElement` 현재 크기 보다 큰 배열의 배열 자동으로 증가에 대 한 호출을 사용 하 여 [CAtlArray::SetCount](#setcount)합니다. 디버그 빌드에서 ATLASSERT 발생 합니다는 `CAtlArray` 개체가 유효 하지 않습니다. 일반 정품 빌드에 잘못 된 매개 변수 예상치 못한 결과가 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&12;](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MMXSwarm 샘플](../../visual-cpp-samples.md)   
 [DynamicConsumer 샘플](../../visual-cpp-samples.md)   
 [UpdatePV 샘플](../../visual-cpp-samples.md)   
 [움직이는 텍스트 샘플](../../visual-cpp-samples.md)   
 [CArray 클래스](../../mfc/reference/carray-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

