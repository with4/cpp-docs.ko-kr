---
title: CTypedPtrArray 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbbe2d9ed6ab7a17ccbd110d12070d4e295a62ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375822"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray 클래스
`CPtrArray` 또는 `CObArray`클래스의 개체에 대해 형식 안전 "래퍼"를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>매개 변수  
 `BASE_CLASS`  
 형식화 된 포인터 배열 클래스;의 기본 클래스 배열 클래스 여야 합니다 ( `CObArray` 또는 `CPtrArray`).  
  
 `TYPE`  
 기본 클래스 배열에 저장 된 요소의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTypedPtrArray::Add](#add)|배열의 끝에 새 요소를 추가합니다. 필요한 경우 배열을 확장합니다|  
|[CTypedPtrArray::Append](#append)|한 배열의 내용을 다른의 끝에 추가합니다. 필요한 경우 배열을 확장합니다|  
|[CTypedPtrArray::Copy](#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|  
|[CTypedPtrArray::ElementAt](#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|  
|[CTypedPtrArray::GetAt](#getat)|지정된 인덱스의 값을 반환합니다.|  
|[CTypedPtrArray::InsertAt](#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|  
|[CTypedPtrArray::SetAt](#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|  
|[CTypedPtrArray::SetAtGrow](#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CTypedPtrArray::operator]](#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 사용 하는 경우 `CTypedPtrArray` 대신 `CPtrArray` 또는 `CObArray`, c + + 형식 검사 기능에 일치 하지 않는 포인터 형식으로 인 한 오류를 제거 하는 데 도움이 됩니다.  
  
 또한는 `CTypedPtrArray` 래퍼를 사용한 경우 필요할 수 캐스팅의 많은 수행 `CObArray` 또는 `CPtrArray`합니다.  
  
 때문에 모든 `CTypedPtrArray` 함수는 인라인, 크기 또는 코드의 속도이 템플릿을 사용 하 여 크게 적용 되지 않습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CTypedPtrArray`, 문서를 참조 [컬렉션](../../mfc/collections.md) 및 [템플릿 기반 클래스](../../mfc/template-based-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtempl.h  
  
##  <a name="add"></a>  CTypedPtrArray::Add  
 이 멤버 함수를 호출 `BASE_CLASS` **:: 추가**합니다.  
  
```  
INT_PTR Add(TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 배열에 추가할 요소의 형식을 지정 하는 템플릿 매개 변수  
  
 `newElement`  
 이 배열에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 요소의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CObArray::Add](../../mfc/reference/cobarray-class.md#add)합니다.  
  
##  <a name="append"></a>  CTypedPtrArray::Append  
 이 멤버 함수를 호출 `BASE_CLASS` **:: Append**합니다.  
  
```  
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>매개 변수  
 `BASE_CLASS`  
 형식화 된 포인터 배열 클래스;의 기본 클래스 배열 클래스 여야 합니다 ( [CObArray](../../mfc/reference/cobarray-class.md) 또는 [사용할 때](../../mfc/reference/cptrarray-class.md)).  
  
 *형식*  
 기본 클래스 배열에 저장 된 요소의 형식입니다.  
  
 *src*  
 소스 배열에 추가할 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 첫 번째 요소의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CObArray::Append](../../mfc/reference/cobarray-class.md#append)합니다.  
  
##  <a name="copy"></a>  CTypedPtrArray::Copy  
 이 멤버 함수를 호출 `BASE_CLASS` **:: Copy**합니다.  
  
```  
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>매개 변수  
 `BASE_CLASS`  
 형식화 된 포인터 배열 클래스;의 기본 클래스 배열 클래스 여야 합니다 ( [CObArray](../../mfc/reference/cobarray-class.md) 또는 [사용할 때](../../mfc/reference/cptrarray-class.md)).  
  
 *형식*  
 기본 클래스 배열에 저장 된 요소의 형식입니다.  
  
 *src*  
 소스 배열에 복사할 요소입니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)합니다.  
  
##  <a name="elementat"></a>  CTypedPtrArray::ElementAt  
 이 인라인 함수가 호출 `BASE_CLASS` **:: ElementAt**합니다.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 이 배열에 저장 된 요소의 형식을 지정 하는 템플릿 매개 변수  
  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 `BASE_CLASS` **:: GetUpperBound**합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에 있는 요소에 대 한 임시 참조 `nIndex`합니다. 이 요소는 템플릿 매개 변수로 지정 된 형식의 *형식*합니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)합니다.  
  
##  <a name="getat"></a>  CTypedPtrArray::GetAt  
 이 인라인 함수가 호출 `BASE_CLASS` **:: GetAt**합니다.  
  
```  
TYPE GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수 배열에 저장 된 요소의 형식을 지정 합니다.  
  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 `BASE_CLASS` **:: GetUpperBound**합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에 있는 요소의 복사본 `nIndex`합니다. 이 요소는 템플릿 매개 변수로 지정 된 형식의 *형식*합니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)  
  
##  <a name="insertat"></a>  CTypedPtrArray::InsertAt  
 이 멤버 함수를 호출 `BASE_CLASS` **:: InsertAt**합니다.  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    TYPE newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 반환 된 값 보다 클 수는 정수 인덱스 [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)합니다.  
  
 *형식*  
 기본 클래스 배열에 저장 된 요소의 형식입니다.  
  
 `newElement`  
 이 배열에 배치할 개체 포인터입니다. A `newElement` 값의 **NULL** ï ´ ù.  
  
 `nCount`  
 이 요소가 해야 하는 횟수 (기본값: 1)를 삽입 합니다.  
  
 `nStartIndex`  
 반환 된 값 보다 클 수는 정수 인덱스 `CObArray::GetUpperBound`합니다.  
  
 `BASE_CLASS`  
 형식화 된 포인터 배열 클래스;의 기본 클래스 배열 클래스 여야 합니다 ( [CObArray](../../mfc/reference/cobarray-class.md) 또는 [사용할 때](../../mfc/reference/cptrarray-class.md)).  
  
 `pNewArray`  
 이 배열에 추가 하는 요소가 포함 된 다른 배열입니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)합니다.  
  
##  <a name="operator_at"></a>  CTypedPtrArray::operator]  
 이러한 인라인 연산자 호출 `BASE_CLASS` **:: operator**합니다.  
  
```  
TYPE& operator[ ](int_ptr nindex);  
TYPE operator[ ](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 템플릿 매개 변수 배열에 저장 된 요소의 형식을 지정 합니다.  
  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 `BASE_CLASS` **:: GetUpperBound**합니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 연산자는 호출 하지 않은 배열에 대 한 **const**, 대입문의 왼쪽 (l-value) 또는 오른쪽 (r-value)에서 사용할 수 있습니다. 에 대 한 두 번째 호출 **const** 배열, 오른쪽 에서만 사용할 수 있습니다.  
  
 라이브러리의 디버그 버전 (중 하나에 대입문의 왼쪽 또는 오른쪽) 아래 첨자 벗어났습니다.이 경우 어설션 합니다.  
  
##  <a name="setat"></a>  CTypedPtrArray::SetAt  
 이 멤버 함수를 호출 `BASE_CLASS` **:: SetAt**합니다.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    TYPE ptr);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 보다 크거나 0에 있는 정수 인덱스 및에서 반환 된 값 보다 작거나 같은 [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)합니다.  
  
 *형식*  
 기본 클래스 배열에 저장 된 요소의 형식입니다.  
  
 *ptr*  
 배열에서 nIndex에서 삽입할 요소에 대 한 포인터입니다. NULL 값이 허용 됩니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)합니다.  
  
##  <a name="setatgrow"></a>  CTypedPtrArray::SetAtGrow  
 이 멤버 함수를 호출 `BASE_CLASS` **:: SetAtGrow**합니다.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    TYPE newElement);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 정수 인덱스는 0 보다 크거나 같은 경우입니다.  
  
 *형식*  
 기본 클래스 배열에 저장 된 요소의 형식입니다.  
  
 `newElement`  
 이 배열에 추가할 개체 포인터입니다. A **NULL** 값은 사용할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [사용할 때 클래스](../../mfc/reference/cptrarray-class.md)   
 [CObArray 클래스](../../mfc/reference/cobarray-class.md)
