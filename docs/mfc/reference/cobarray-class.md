---
title: "CObArray 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs: C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87b73299c64d6657d099b3dea9817c08649080df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cobarray-class"></a>CObArray 클래스
`CObject` 포인터 배열을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CObArray : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CObArray::CObArray](#cobarray)|에 대 한 빈 배열을 생성 `CObject` 포인터입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CObArray::Add](#add)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|  
|[CObArray::Append](#append)|배열에 다른 배열을 추가하고 필요하면 배열을 확장합니다.|  
|[CObArray::Copy](#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|  
|[CObArray::ElementAt](#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|  
|[CObArray::FreeExtra](#freeextra)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|  
|[CObArray::GetAt](#getat)|지정된 인덱스의 값을 반환합니다.|  
|[CObArray::GetCount](#getcount)|이 배열에 있는 요소의 수를 가져옵니다.|  
|[CObArray::GetData](#getdata)|배열의 요소에 대한 액세스를 허용합니다. 수 **NULL**합니다.|  
|[CObArray::GetSize](#getsize)|이 배열에 있는 요소의 수를 가져옵니다.|  
|[CObArray::GetUpperBound](#getupperbound)|유효한 최대 인덱스를 반환합니다.|  
|[CObArray::InsertAt](#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|  
|[CObArray::IsEmpty](#isempty)|배열이 비어 있는지를 확인합니다.|  
|[CObArray::RemoveAll](#removeall)|이 배열의 모든 요소를 반환합니다.|  
|[CObArray::RemoveAt](#removeat)|특정 인덱스의 요소를 제거합니다.|  
|[CObArray::SetAt](#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|  
|[CObArray::SetAtGrow](#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|  
|[CObArray::SetSize](#setsize)|이 배열에 포함된 요소의 수를 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CObArray::operator]](#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이러한 개체 배열은 C 배열과 유사 하지만 동적으로 축소 하 고 필요에 따라 증가할 수 있습니다.  
  
 배열 인덱스는 항상 0 위치부터 시작 합니다. 상한 값을 수정 하거나 현재 경계를 지난 요소를 추가 하면 확장 배열 것인지를 결정할 수 있습니다. 메모리는 일부 요소가 null 하는 경우에 상한 값을 연속적으로 할당 됩니다.  
  
 Win32,의 크기는 `CObArray` 개체 사용 가능한 메모리에만 제한 됩니다.  
  
 C 배열에 대 한 액세스 시간과 마찬가지로 `CObArray` 인덱싱된 요소는 상수와 배열 크기와 무관 합니다.  
  
 `CObArray`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다. 배열 하는 경우 `CObject` 포인터 오버 로드 된 삽입 연산자 또는으로 보관 파일로 저장 됩니다는 `Serialize` 멤버 함수를 각각 `CObject` 요소 배열 인덱스와 함께 직렬화 차례로, 합니다.  
  
 개인의 덤프 해야 할 경우 `CObject` 배열의 요소 깊이를 설정 해야 합니다는 `CDumpContext` 개체 1 이상입니다.  
  
 경우는 `CObArray` 개체를 삭제 하거나 때 해당 요소를 제거할만 `CObject` 제거 되 고 포인터, 참조 하는 개체가 아니라 합니다.  
  
> [!NOTE]
>  배열을 사용하기 전에 `SetSize`를 사용하여 배열 크기를 설정하고 배열에 대해 메모리를 할당합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.  
  
 배열 클래스를 파생 목록 파생 하는 것과 비슷합니다. 에 특수 한 용도의 목록 클래스의 파생에 대 한 내용은 문서 참조 [컬렉션](../../mfc/collections.md)합니다.  
  
> [!NOTE]
>  사용 해야 합니다는 `IMPLEMENT_SERIAL` 배열을 serialize 하려는 경우 파생 된 클래스의 구현에는 매크로입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObArray`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcoll.h  
  
##  <a name="add"></a>CObArray::Add  
 1 씩 증가 하는 배열을 배열의 끝에 새 요소를 추가 합니다.  
  
```  
INT_PTR Add(CObject* newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `newElement`  
 `CObject` 이 배열에 추가할 수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 요소의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 경우 [SetSize](#setsize) 함께 사용 된는 `nGrowBy` 추가 메모리를 1 보다 큰 값을 할당할 수 있습니다. 그러나 상한만 1 씩 증가 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::Add`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR 추가 (바이트** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR 추가 (DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**INT_PTR 추가 (void\***  `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR 추가 (LPCTSTR** `newElement` **); throw (CMemoryException\* );**<br /><br /> **INT_PTR Add(const CString&** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR 추가 (UINT** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR 추가 (WORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>예  
  참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `Add example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $442A 21`  
  
 `[1] = a CAge at $4468 40`  
  
##  <a name="append"></a>CObArray::Append  
 다른 배열의 내용을 지정 된 배열의 끝에 추가 하려면이 함수를 호출 합니다.  
  
```  
INT_PTR Append(const CObArray& src);
```  
  
### <a name="parameters"></a>매개 변수  
 *src*  
 소스 배열에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 첫 번째 요소의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 배열이 동일한 형식 이어야 합니다.  
  
 필요한 경우 **Append** 배열에 추가 된 요소를 수용 하기 위해 추가 메모리를 할당할 수 있습니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::Append`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR 추가 (const CByteArray &** *src* **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR 추가 (const CDWordArray &** *src* **);**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**INT_PTR 추가 (const 사용할 때 &** *src* **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR 추가 (const CStringArray &** *src* **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR 추가 (const CUIntArray &** *src* **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR 추가 (const CWordArray &** *src* **);**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]  
  
##  <a name="copy"></a>CObArray::Copy  
 동일한 형식의 다른 배열의 요소와 지정 된 배열의 요소를 덮어쓰려면이 멤버 함수를 호출 합니다.  
  
```  
void Copy(const CObArray& src);
```  
  
### <a name="parameters"></a>매개 변수  
 *src*  
 요소를 배열에 복사의 원본입니다.  
  
### <a name="remarks"></a>설명  
 **복사** 메모리를 해제 하지는 않습니다; 하지만 필요한 경우 **복사** 배열에 복사 된 요소를 수용 하기 위해 추가 메모리를 할당할 수 있습니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::Copy`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**복사 void (const CByteArray &** *src* **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**복사 void (const CDWordArray &** *src* **);**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**복사 void (const 사용할 때 &** *src* **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**복사 void (const CStringArray &** *src* **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**복사 void (const CUIntArray &** *src* **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**복사 void (const CWordArray &** *src* **);**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]  
  
##  <a name="cobarray"></a>CObArray::CObArray  
 빈 생성 `CObject` 포인터 배열입니다.  
  
```  
CObArray();
```  
  
### <a name="remarks"></a>설명  
 한 번에 하나의 요소가 증가 하는 배열 합니다.  
  
 다음 표에서 비슷합니다는 다른 생성자를 보여 줍니다. `CObArray::CObArray`합니다.  
  
|클래스|생성자|  
|-----------|-----------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray ();**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**사용할 때 ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray ();**|  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]  
  
##  <a name="elementat"></a>CObArray::ElementAt  
 배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.  
  
```  
CObject*& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 `GetUpperBound`합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조는 `CObject` 포인터입니다.  
  
### <a name="remarks"></a>설명  
 배열에 대 한 왼쪽 할당 연산자를 구현 하는 데 사용 됩니다. 이 특수 배열 연산을 구현에 사용 해야 하는 고급 함수 note 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::ElementAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**바이트 및 ElementAt (INT_PTR** `nIndex` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & ElementAt (INT_PTR** `nIndex` **);**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**void\*& ElementAt (INT_PTR** `nIndex` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & ElementAt (INT_PTR** `nIndex` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT & ElementAt (INT_PTR** `nIndex` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD 및 ElementAt (INT_PTR** `nIndex` **);**|  
  
### <a name="example"></a>예  
  예를 참조 [CObArray::GetSize](#getsize)합니다.  
  
##  <a name="freeextra"></a>CObArray::FreeExtra  
 배열 된 증가 하는 동안 할당 된 모든 추가 메모리를 해제 합니다.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>설명  
 이 함수는 크기 또는 배열의 상한에 영향을 주지 않습니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::FreeExtra`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void FreeExtra ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void FreeExtra ();**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**void FreeExtra ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void FreeExtra ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void FreeExtra ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void FreeExtra ();**|  
  
### <a name="example"></a>예  
  예를 참조 [CObArray::GetData](#getdata)합니다.  
  
##  <a name="getat"></a>CObArray::GetAt  
 지정된 된 인덱스에 있는 배열 요소를 반환합니다.  
  
```  
CObject* GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 `GetUpperBound`합니다.  
  
### <a name="return-value"></a>반환 값  
 `CObject` 이 인덱스에 현재 포인터 요소입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  반환 된 값 보다 큰 음수 값 또는 값을 전달 `GetUpperBound` 실패 한 어설션이 발생 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::GetAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**바이트 GetAt (INT_PTR** `nIndex` **) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const;**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**void\* GetAt (INT_PTR** `nIndex` **) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR** `nIndex` **) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]  
  
##  <a name="getcount"></a>CObArray::GetCount  
 배열 요소의 수를 반환합니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 배열의 항목 수입니다.  
  
### <a name="remarks"></a>설명  
 배열의 요소 수를 검색 하려면이 메서드를 호출 합니다. 인덱스가 0부터 시작 하기 때문에 크기는 1 가장 큰 인덱스 보다 큽니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::GetCount`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Const; INT_PTR GetCount)**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Const; INT_PTR GetCount)**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**Const; INT_PTR GetCount)**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Const; INT_PTR GetCount)**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Const; INT_PTR GetCount)**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]  
  
##  <a name="getdata"></a>CObArray::GetData  
 이 멤버 함수를 사용 하 여 배열의 요소에 직접 액세스할 수 있습니다.  
  
```  
const CObject** GetData() const;  
  
CObject** GetData();
```  
  
### <a name="return-value"></a>반환 값  
 배열에 대 한 포인터 `CObject` 포인터입니다.  
  
### <a name="remarks"></a>설명  
 요소가 없는 경우 `GetData` null 값을 반환 합니다.  
  
 배열 요소에 대 한 직접 액세스를 손쉽게 보다 신속 하 게 작업할 수 있습니다를 사용 하 여 주의 호출할 때 `GetData`; 직접적 오류 배열 요소에 영향을 줍니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::GetData`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const 바이트\* const; GetData) 바이트\* GetData ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData () const; DWORD\* GetData ();**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**const void\* \* GetData () const; void\* \* GetData ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* const; GetData) CString\* GetData ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT\* const; GetData) UINT\* GetData ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const 단어\* const; GetData) WORD\* GetData ();**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]  
  
##  <a name="getsize"></a>CObArray::GetSize  
 배열의 크기를 반환합니다.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>설명  
 인덱스와 0부터 시작 되므로 크기는 1 가장 큰 인덱스 보다 큽니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::GetSize`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Const; INT_PTR GetSize)**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Const; INT_PTR GetSize)**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**Const; INT_PTR GetSize)**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Const; INT_PTR GetSize)**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Const; INT_PTR GetSize)**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>CObArray::GetUpperBound  
 이 배열의 현재 상한 값을 반환합니다.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="return-value"></a>반환 값  
 인덱스 (0부터 시작) 상한입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 값 1을 반환 배열 인덱스가 0부터 시작 하기 때문에 보다 작은 `GetSize`합니다.  
  
 조건이 **GetUpperBound ()** =-1 배열에 요소가 포함 되어 있음을 나타냅니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::GetUpperBound`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Const; INT_PTR GetUpperBound)**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Const; INT_PTR GetUpperBound)**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**Const; INT_PTR GetUpperBound)**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Const; INT_PTR GetUpperBound)**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Const; INT_PTR GetUpperBound)**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Const; INT_PTR GetUpperBound)**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]  
  
##  <a name="insertat"></a>CObArray::InsertAt  
 지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    CObject* newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CObArray* pNewArray);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 반환 된 값 보다 클 수는 정수 인덱스 `GetUpperBound`합니다.  
  
 `newElement`  
 `CObject` 이 배열에 배치할 수에 대 한 포인터입니다. A `newElement` 값의 **NULL** ï ´ ù.  
  
 `nCount`  
 이 요소가 해야 하는 횟수 (기본값: 1)를 삽입 합니다.  
  
 `nStartIndex`  
 반환 된 값 보다 클 수는 정수 인덱스 `GetUpperBound`합니다.  
  
 `pNewArray`  
 이 배열에 추가 하는 요소가 포함 된 다른 배열입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전 `InsertAt` 배열에서 지정된 된 인덱스에 요소 하나 (또는 요소가 여러 개)를 삽입 합니다. 프로세스에서 이동 (인덱스 증가) 하 여이 인덱스에서 기존 요소 위에 있는 모든 요소를 이동 합니다.  
  
 두 번째 버전에서 다른 모든 요소를 삽입 한 `CObArray` 에서 시작 하는 컬렉션의 `nStartIndex` 위치입니다.  
  
 `SetAt` 반면, 함수 한 지정 된 배열 요소를 대체 하 고 모든 요소를 이동 하지 않습니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::InsertAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**InsertAt void (INT_PTR** `nIndex` **, 바이트** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **InsertAt void (INT_PTR** `nStartIndex` **, CByteArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**InsertAt void (INT_PTR** `nIndex` **, DWORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **InsertAt void (INT_PTR** `nStartIndex` **, CDWordArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**InsertAt void (INT_PTR** `nIndex` **, void\***  `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **InsertAt void (INT_PTR** `nStartIndex` **를 사용할 때\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**InsertAt void (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **InsertAt void (INT_PTR** `nStartIndex` **, CStringArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**InsertAt void (INT_PTR** `nIndex` **, UINT** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **InsertAt void (INT_PTR** `nStartIndex` **, CUIntArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**InsertAt void (INT_PTR** `nIndex` **, WORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **InsertAt void (INT_PTR** `nStartIndex` **, CWordArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>예  
  참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `InsertAt example: A CObArray with 3 elements`  
  
 `[0] = a CAge at $45C8 21`  
  
 `[1] = a CAge at $4646 30`  
  
 `[2] = a CAge at $4606 40`  
  
##  <a name="isempty"></a>CObArray::IsEmpty  
 배열이 비어 있는지를 확인합니다.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>반환 값  
 배열이 비어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="operator_at"></a>CObArray::operator]  
 이러한 아래 첨자 연산자는 편리 하 게 대체는 `SetAt` 및 `GetAt` 함수입니다.  
  
```  
CObject*& operator[](int_ptr nindex);  
CObject* operator[](int_ptr nindex) const;  
```  
  
### <a name="remarks"></a>설명  
 첫 번째 연산자는 호출 하지 않은 배열에 대 한 **const**, 대입문의 왼쪽 (l-value) 또는 오른쪽 (r-value)에서 사용할 수 있습니다. 에 대 한 두 번째 호출 **const** 배열, 오른쪽에만 사용할 수 있습니다.  
  
 라이브러리의 디버그 버전 (중 하나에 대입문의 왼쪽 또는 오른쪽) 아래 첨자 벗어났습니다.이 경우 어설션 합니다.  
  
 다음 표에서 다른 연산자와 유사한 **CObArray::operator**합니다.  
  
|클래스|연산자|  
|-----------|--------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**바이트 & 연산자 (int_ptr** `nindex`  **\);**<br /><br /> **BYTE 연산자 (int_ptr** `nindex`  **\) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & 연산자 (int_ptr** `nindex`  **\);**<br /><br /> **DWORD 연산자 (int_ptr** `nindex`  **\) const;**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**void\*& 연산자 (int_ptr** `nindex`  **\);**<br /><br /> **void\* 연산자 (int_ptr** `nindex`  **\) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & 연산자 (int_ptr** `nindex`  **\);**<br /><br /> **CString 연산자 (int_ptr** `nindex`  **\) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT & 연산자 (int_ptr** `nindex`  **\);**<br /><br /> **UINT 연산자 (int_ptr** `nindex`  **\) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & 연산자 (int_ptr** `nindex`  **\);**<br /><br /> **WORD 연산자 (int_ptr** `nindex`  **\) const;**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]  
  
##  <a name="removeall"></a>CObArray::RemoveAll  
 이 배열에서 모든 포인터를 제거 하지만 실제로 삭제 하지 않습니다는 `CObject` 개체입니다.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>설명  
 배열이 비어 이미 함수는 계속 작동 합니다.  
  
 `RemoveAll` 함수 포인터 저장에 사용 되는 모든 메모리를 해제 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::RemoveAll`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAll ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAll ();**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**void RemoveAll ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAll ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAll ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAll ();**|  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]  
  
##  <a name="removeat"></a>CObArray::RemoveAt  
 배열에서 지정 된 인덱스에서 시작 하는 하나 이상의 요소를 제거 합니다.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 `GetUpperBound`합니다.  
  
 `nCount`  
 제거할 요소의 수입니다.  
  
### <a name="remarks"></a>설명  
 프로세스에서 제거 된 요소 위에 있는 모든 요소를 아래로 이동합니다. 그 감소 위 배열의 바인딩되지만 메모리를 해제 하지는 않습니다.  
  
 제거 지점 위에 배열에 포함 된 보다 더 많은 요소를 제거 하려고 할 경우 라이브러리의 디버그 버전 어설션 합니다.  
  
 `RemoveAt` 제거 함수는 `CObject` 하지만 배열에서 포인터는 개체 자체가 삭제 되지 않습니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::RemoveAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**RemoveAt void (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**RemoveAt void (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**RemoveAt void (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**RemoveAt void (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**RemoveAt void (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**RemoveAt void (INT_PTR** `nIndex` **, INT_PTR** *nCount* **= 1);**|  
  
### <a name="example"></a>예  
  참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `RemoveAt example: A CObArray with 1 elements`  
  
 `[0] = a CAge at $4606 40`  
  
##  <a name="setat"></a>CObArray::SetAt  
 지정된 된 인덱스에 있는 배열 요소를 설정합니다.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 `GetUpperBound`합니다.  
  
 `newElement`  
 이 배열에 삽입할 개체 포인터입니다. A **NULL** 값은 사용할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 `SetAt`증가 배열을 발생 하지 않습니다. 사용 하 여 `SetAtGrow` 배열 자동으로 증가 하도록 하려는 경우.  
  
 인덱스 값 배열에서 올바른 위치를 나타내도록 확인 해야 합니다. 범위를 벗어나는 경우 라이브러리의 디버그 버전 어설션 합니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::SetAt`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**SetAt void (INT_PTR** `nIndex` **, 바이트** `newElement` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**SetAt void (INT_PTR** `nIndex` **, DWORD** `newElement` **);**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**SetAt void (INT_PTR** `nIndex` **, void\***  `newElement` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**SetAt void (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**SetAt void (INT_PTR** `nIndex` **, UINT** `newElement` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**SetAt void (INT_PTR** `nIndex` **, WORD** `newElement` **);**|  
  
### <a name="example"></a>예  
  참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `SetAt example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $47E0 30`  
  
 `[1] = a CAge at $47A0 40`  
  
##  <a name="setatgrow"></a>CObArray::SetAtGrow  
 지정된 된 인덱스에 있는 배열 요소를 설정합니다.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 정수 인덱스는 0 보다 크거나 같은 경우입니다.  
  
 `newElement`  
 이 배열에 추가할 개체 포인터입니다. A **NULL** 값은 사용할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 필요한 경우 배열 자동으로 증가 (상한 하 여 새 요소로 적용 하도록 조정 됩니다.).  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::SetAtGrow`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**SetAtGrow void (INT_PTR** `nIndex` **, 바이트** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**SetAtGrow void (INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**SetAtGrow void (INT_PTR** `nIndex` **, void\***  `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**SetAtGrow void (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**SetAtGrow void (INT_PTR** `nIndex` **, UINT** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**SetAtGrow void (INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>예  
  참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 컬렉션의 모든 예제에서 사용 되는 클래스입니다.  
  
 [!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]  
  
 이 프로그램에서 결과 다음과 같습니다.  
  
 `SetAtGrow example: A CObArray with 4 elements`  
  
 `[0] = a CAge at $47C0 21`  
  
 `[1] = a CAge at $4800 40`  
  
 `[2] = NULL`  
  
 `[3] = a CAge at $4840 65`  
  
##  <a name="setsize"></a>CObArray::SetSize  
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
 새 크기가 원래 크기 보다 작은 경우 배열이 잘리고 하 고 사용 하지 않는 모든 메모리 해제 됩니다. 효율성을 높이기 위해 호출 `SetSize` 사용 하기 전에 배열의 크기를 설정할 수 있습니다. 이렇게 하면 다시 할당 하 고 항목이 추가 될 때마다 배열을 복사 필요 합니다.  
  
 `nGrowBy` 매개 변수 배열의 증가 하는 동안 내부 메모리 할당에 영향을 줍니다. 사용에 영향을 주지 배열 크기에서 보고 `GetSize` 및 `GetUpperBound`합니다.  
  
 배열의 크기 증가 하는 경우 새로 할당 된 **CObject \***  포인터를 NULL로 설정 됩니다.  
  
 다음 표에서 함수를 보여 줍니다 다른 멤버와 유사한 `CObArray::SetSize`합니다.  
  
|클래스|멤버 함수|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException\* );**|  
|[사용할 때](../../mfc/reference/cptrarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>예  
  예를 참조 [CObArray::GetData](#getdata)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CStringArray 클래스](../../mfc/reference/cstringarray-class.md)   
 [사용할 때 클래스](../../mfc/reference/cptrarray-class.md)   
 [CByteArray 클래스](../../mfc/reference/cbytearray-class.md)   
 [CWordArray 클래스](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray 클래스](../../mfc/reference/cdwordarray-class.md)
