---
title: CArray 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
dev_langs:
- CPP
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e4e4fd0106687927706b0ba303035258de7e651
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="carray-class"></a>CArray 클래스
C 배열과 유사 하지만 동적으로 줄일 수 필요에 따라 증가 하는 배열을 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TYPE`  
 배열에 저장 된 개체의 형식을 지정 하는 템플릿 매개 변수입니다. `TYPE` 반환 하는 매개 변수 `CArray`합니다.  
  
 `ARG` *_* `TYPE`  
 배열에 저장 된 개체에 액세스 하는 데 사용 되는 인수 형식을 지정 하는 템플릿 매개 변수 에 대 한 참조 종종 `TYPE`합니다. `ARG_TYPE` 에 전달 되는 매개 변수 `CArray`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CArray::CArray](#carray)|빈 배열을 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CArray::Add](#add)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|  
|[CArray::Append](#append)|배열;에 다른 배열을 추가합니다 필요한 경우 배열을 확장합니다|  
|[CArray::Copy](#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|  
|[CArray::ElementAt](#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|  
|[CArray::FreeExtra](#freeextra)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|  
|[CArray::GetAt](#getat)|지정된 인덱스의 값을 반환합니다.|  
|[CArray::GetCount](#getcount)|이 배열에 있는 요소의 수를 가져옵니다.|  
|[CArray::GetData](#getdata)|배열의 요소에 대한 액세스를 허용합니다. 수 **NULL**합니다.|  
|[CArray::GetSize](#getsize)|이 배열에 있는 요소의 수를 가져옵니다.|  
|[CArray::GetUpperBound](#getupperbound)|유효한 최대 인덱스를 반환합니다.|  
|[CArray::InsertAt](#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|  
|[CArray::IsEmpty](#isempty)|배열이 비어 있는지 여부를 결정 합니다.|  
|[CArray::RemoveAll](#removeall)|이 배열의 모든 요소를 반환합니다.|  
|[CArray::RemoveAt](#removeat)|특정 인덱스의 요소를 제거합니다.|  
|[CArray::SetAt](#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|  
|[CArray::SetAtGrow](#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|  
|[CArray::SetSize](#setsize)|이 배열에 포함된 요소의 수를 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator&#91;&#93;](#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 배열 인덱스는 항상 0 위치부터 시작 합니다. 상한 값을 수정 하거나 현재 바인딩된 지난 요소를 추가 하면 확장에 배열 사용을 여부를 결정할 수 있습니다. 메모리는 일부 요소가 null 하는 경우에 상한 값을 연속적으로 할당 됩니다.  
  
> [!NOTE]
>  크기를 조정 하는 대부분의 메서드는 `CArray` 개체 또는 요소를 사용 하 여 추가 [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) 요소를 이동 합니다. 이것은 문제 때문에 `memcpy_s` 생성자를 호출할지 필요로 하는 모든 개체와 호환 되지 않습니다. 경우에 있는 항목의 `CArray` 와 호환 되지 않는 `memcpy_s`, 새 만들어야 `CArray` 적절 한 크기의 합니다. 사용 해야 [CArray::Copy](#copy) 및 [CArray::SetAt](#setat) 이러한 메서드는 할당 연산자를 대신 사용 하기 때문에 새 배열을 채울 `memcpy_s`합니다.  
  
 C 배열에 대 한 액세스 시간과 마찬가지로 `CArray` 인덱싱된 요소는 상수와 배열 크기와 무관 합니다.  
  
> [!TIP]
>  배열을 사용 하기 전에 사용 하 여 [SetSize](#setsize) 크기로 설정 하 고에 대 한 메모리를 할당 합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.  
  
 배열에 있는 개별 요소의 덤프가 필요 하면의 깊이 설정 해야는 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 1 또는 더 큰 개체입니다.  
  
 글로벌 도우미 함수를이 클래스 호출의 특정 멤버 함수는 대부분 용도에 대 한 사용자 지정 되어야 합니다는 `CArray` 클래스입니다. 항목을 참조 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) MFC 매크로 및 전역 섹션에 있습니다.  
  
 배열 클래스를 파생 목록 파생과 비슷합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CArray`, 문서를 참조 [컬렉션](../../mfc/collections.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>요구 사항  
 `Header:` afxtempl.h  
  
##  <a name="add"></a>  CArray::Add  
 1 씩 증가 하는 배열을 배열의 끝에 새 요소를 추가 합니다.  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `ARG_TYPE`  
 이 배열의 요소를 참조 하는 인수의 형식을 지정 하는 템플릿 매개 변수  
  
 `newElement`  
 이 배열에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 요소의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 경우 [SetSize](#setsize) 함께 사용 된는 `nGrowBy` 추가 메모리를 1 보다 큰 값을 할당할 수 있습니다. 그러나 상한만 1 씩 증가 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>  CArray::Append  
 한 배열의 내용을 다른의 끝에 추가 하려면이 함수를 호출 합니다.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>매개 변수  
 *src*  
 소스 배열에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 첫 번째 요소의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 배열이 동일한 형식 이어야 합니다.  
  
 필요한 경우 **Append** 배열에 추가 된 요소를 수용 하기 위해 추가 메모리를 할당할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>  CArray::CArray  
 빈 배열을 생성합니다.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>설명  
 한 번에 하나의 요소가 증가 하는 배열 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>  CArray::Copy  
 이 멤버 함수를 사용 하 여 다른 한 배열의 요소를 복사 합니다.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>매개 변수  
 *src*  
 소스 배열에 복사할 요소입니다.  
  
### <a name="remarks"></a>설명  
 다른 배열의 요소와 한 배열의 요소를 덮어쓰려면이 멤버 함수를 호출 합니다.  
  
 **복사** 메모리를 해제 하지는 않습니다; 하지만 필요한 경우 **복사** 배열에 복사 된 요소를 수용 하기 위해 추가 메모리를 할당할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CArray::ElementAt  
 배열 내에서 지정된 된 요소에 대 한 임시 참조를 반환합니다.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 [GetUpperBound](#getupperbound)합니다.  
  
### <a name="return-value"></a>반환 값  
 배열 요소에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 배열에 대 한 왼쪽 할당 연산자를 구현 하는 데 사용 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [GetSize](#getsize)합니다.  
  
##  <a name="freeextra"></a>  CArray::FreeExtra  
 배열 된 증가 하는 동안 할당 된 모든 추가 메모리를 해제 합니다.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>설명  
 이 함수는 크기 또는 배열의 상한에 영향을 주지 않습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [GetData](#getdata)합니다.  
  
##  <a name="getat"></a>  CArray::GetAt  
 지정된 된 인덱스에 있는 배열 요소를 반환합니다.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수는 배열 요소의 형식을 지정 합니다.  
  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 [GetUpperBound](#getupperbound)합니다.  
  
### <a name="return-value"></a>반환 값  
 이 인덱스에 현재 있는 배열 요소입니다.  
  
### <a name="remarks"></a>설명  
 반환 된 값 보다 큰 음수 값 또는 값을 전달 `GetUpperBound` 실패 한 어설션이 발생 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>  CArray::GetCount  
 배열 요소의 수를 반환합니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 배열의 항목 수입니다.  
  
### <a name="remarks"></a>설명  
 배열의 요소 수를 검색 하려면이 메서드를 호출 합니다. 인덱스가 0부터 시작 하기 때문에 크기는 1 가장 큰 인덱스 보다 큽니다. 이 메서드를 호출 하면 동일한 결과를 생성 합니다는 [CArray::GetSize](#getsize) 메서드.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CArray::GetData  
 이 멤버 함수를 사용 하 여 배열에 있는 요소에 직접 액세스할 수 있습니다.  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수는 배열 요소의 형식을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 배열 요소에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 요소가 없는 경우 `GetData` null 값을 반환 합니다.  
  
 배열 요소에 대 한 직접 액세스를 손쉽게 보다 신속 하 게 작업할 수 있습니다를 사용 하 여 주의 호출할 때 `GetData`; 직접적 오류 배열 요소에 영향을 줍니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>  CArray::GetSize  
 배열의 크기를 반환합니다.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>설명  
 인덱스가 0부터 시작 하기 때문에 크기는 1 가장 큰 인덱스 보다 큽니다. 이 메서드를 호출 하면 동일한 결과를 생성 합니다는 [CArray::GetCount](#getcount) 메서드.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CArray::GetUpperBound  
 이 배열의 현재 상한 값을 반환합니다.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>설명  
 이 함수는 값 1을 반환 배열 인덱스가 0부터 시작 하기 때문에 보다 작은 `GetSize`합니다.  
  
 조건이 **GetUpperBound ()** =-1 배열에 요소가 포함 되어 있음을 나타냅니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CArray::GetAt](#getat)합니다.  
  
##  <a name="insertat"></a>  CArray::InsertAt  
 첫 번째 버전 `InsertAt` 배열에서 지정된 된 인덱스에 요소 하나 (또는 요소가 여러 개)를 삽입 합니다.  
  
```  
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,  
    INT_PTR nCount = 1);
 
void InsertAt(
    INT_PTR nStartIndex,  
    CArray* pNewArray);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 반환 된 값 보다 클 수는 정수 인덱스 `GetUpperBound`합니다.  
  
 `ARG_TYPE`  
 이 배열에 있는 요소의 형식을 지정 하는 템플릿 매개 변수  
  
 `newElement`  
 이 배열에 배치 될 요소입니다.  
  
 `nCount`  
 이 요소가 해야 하는 횟수 (기본값: 1)를 삽입 합니다.  
  
 `nStartIndex`  
 반환 된 값 보다 클 수는 정수 인덱스 [GetUpperBound](#getupperbound)합니다.  
  
 `pNewArray`  
 이 배열에 추가 하는 요소가 포함 된 다른 배열입니다.  
  
### <a name="remarks"></a>설명  
 프로세스에서 이동 (인덱스 증가) 하 여이 인덱스에서 기존 요소 위에 있는 모든 요소를 이동 합니다.  
  
 두 번째 버전에서 다른 모든 요소를 삽입 한 `CArray` 에서 시작 하는 컬렉션의 `nStartIndex` 위치입니다.  
  
 `SetAt` 반면, 함수 한 지정 된 배열 요소를 대체 하 고 모든 요소를 이동 하지 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CArray::IsEmpty  
 배열이 비어 있는지 여부를 결정 합니다.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>반환 값  
 배열에 요소가; 없으면 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="operator_at"></a>  CArray::operator \[\]  
 이러한 아래 첨자 연산자는 편리 하 게 대체는 [SetAt](#setat) 및 [GetAt](#getat) 함수입니다.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 이 배열에 있는 요소의 형식을 지정 하는 템플릿 매개 변수  
  
 `nIndex`  
 에 액세스 하는 요소의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 연산자는 호출 하지 않은 배열에 대 한 **const**, 대입문의 왼쪽 (l-value) 또는 오른쪽 (r-value)에서 사용할 수 있습니다. 에 대 한 두 번째 호출 **const** 배열, 오른쪽에만 사용할 수 있습니다.  
  
 라이브러리의 디버그 버전 (중 하나에 대입문의 왼쪽 또는 오른쪽) 아래 첨자 벗어났습니다.이 경우 어설션 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="relocateelements"></a>  CArray::RelocateElements  
 배열 확대 되거나 축소 하는 경우 새 버퍼에 데이터를 재배치 됩니다.  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>매개 변수  
 `pNewData`  
 배열 요소에 대 한 새 버퍼입니다.  
  
 `pData`  
 이전 배열 요소입니다.  
  
 `nCount`  
 이전 배열의 요소 수입니다.  
  
### <a name="remarks"></a>설명  
 `pNewData` 항상 모든 포함할 수 있는 크기는 `pData` 요소입니다.  
  
 [CArray](../../mfc/reference/carray-class.md) 구현 배열 확대 되거나 축소 하는 경우 이전 데이터를 새 버퍼를 복사 하려면이 메서드를 사용 합니다 (때 [SetSize](#setsize) 또는 [FreeExtra](#freeextra) 호출). 기본 구현은 데이터를 복사합니다.  
  
 배열 요소 포함 해당 멤버 중 하나에 대 한 포인터 또는 배열 요소 중 하나에 대 한 포인터를 포함 하는 다른 구조에 대 한 포인터 일반 복사에서 업데이트 되지 않습니다. 이 경우의 특수화를 구현 하 여 포인터를 수정할 수 있습니다 `RelocateElements` 관련 형식을 사용 합니다. 데이터 복사 작업을 담당 수도 있습니다.  
  
##  <a name="removeall"></a>  CArray::RemoveAll  
 이 배열의 모든 요소를 반환합니다.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>설명  
 배열이 비어 이미 함수는 계속 작동 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="removeat"></a>  CArray::RemoveAt  
 배열에서 지정 된 인덱스에서 시작 하는 하나 이상의 요소를 제거 합니다.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 [GetUpperBound](#getupperbound)합니다.  
  
 `nCount`  
 제거할 요소의 수입니다.  
  
### <a name="remarks"></a>설명  
 프로세스에서 제거 된 요소 위에 있는 모든 요소를 아래로 이동합니다. 그 감소 위 배열의 바인딩되지만 메모리를 해제 하지는 않습니다.  
  
 제거 지점 위에 배열에 포함 된 보다 더 많은 요소를 제거 하려고 할 경우 라이브러리의 디버그 버전 어설션 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>  CArray::SetAt  
 지정된 된 인덱스에 있는 배열 요소를 설정합니다.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 [GetUpperBound](#getupperbound)합니다.  
  
 `ARG_TYPE`  
 템플릿 매개 변수를 배열 요소를 참조 하기 위해 사용 되는 인수 형식을 지정 합니다.  
  
 `newElement`  
 지정된 된 위치에 저장 하려면 새 요소 값입니다.  
  
### <a name="remarks"></a>설명  
 `SetAt` 증가 배열을 발생 하지 않습니다. 사용 하 여 [SetAtGrow](#setatgrow) 배열 자동으로 증가 하도록 하려는 경우.  
  
 인덱스 값 배열에서 올바른 위치를 나타내도록 확인 해야 합니다. 범위를 벗어나는 경우 라이브러리의 디버그 버전 어설션 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [GetAt](#getat)합니다.  
  
##  <a name="setatgrow"></a>  CArray::SetAtGrow  
 지정된 된 인덱스에 있는 배열 요소를 설정합니다.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 정수 인덱스는 0 보다 크거나 같은 경우입니다.  
  
 `ARG_TYPE`  
 배열에서 요소 형식을 지정 하는 템플릿 매개 변수  
  
 `newElement`  
 이 배열에 추가할 요소입니다. A **NULL** 값은 사용할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 필요한 경우 배열 자동으로 증가 (상한 하 여 새 요소로 적용 하도록 조정 됩니다.).  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>  CArray::SetSize  
 비어 있거나 기존 배열의; 크기를 설정합니다. 필요한 경우 메모리를 할당 합니다.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewSize`  
 새 배열 크기 (요소 수)입니다. 보다 크거나 0 이어야 합니다.  
  
 `nGrowBy`  
 최소 크기 증가 사용 하는 필요한 경우 할당할 슬롯 요소 수입니다.  
  
### <a name="remarks"></a>설명  
 새 크기가 원래 크기 보다 작은 경우 배열이 잘리고 하 고 사용 하지 않는 모든 메모리 해제 됩니다.  
  
 배열을 사용 하기 전에 배열 크기를 설정 하려면이 함수를 사용 합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.  
  
 `nGrowBy` 매개 변수 배열의 증가 하는 동안 내부 메모리 할당에 영향을 줍니다. 사용에 영향을 주지 배열 크기에서 보고 [GetSize](#getsize) 및 [GetUpperBound](#getupperbound)합니다. 기본값을 사용 하는 경우 MFC 메모리 조각화를 방지 하 고 대부분의 경우에 대 한 효율을 최적화 하기 위해 계산 방식으로 메모리를 할당 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [GetData](#getdata)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObArray 클래스](../../mfc/reference/cobarray-class.md)   
 [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md)
