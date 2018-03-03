---
title: "컬렉션 클래스 도우미 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82b11c4cbe8f862121d89c308ab11d53582931d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="collection-class-helpers"></a>컬렉션 클래스 도우미
컬렉션 클래스 `CMap`, `CList`, 및 `CArray` 를 비교 하 고, 복사 및 요소를 직렬화 하는 작업에 대 한 전역 템플릿 기반 도우미 함수를 사용 합니다. 구현에 따라 클래스의 일부로 `CMap`, `CList`, 및 `CArray`, 지도, 목록 또는 배열에 저장 된 데이터의 형식에 맞는 버전 필요에 따라 이러한 함수를 재정의 해야 합니다. 와 같은 도우미 함수를 재정의에 대 한 내용은 `SerializeElements`, 문서를 참조 [컬렉션: 형식이 안전한 컬렉션을 만드는 방법](../../mfc/how-to-make-a-type-safe-collection.md)합니다. **ConstructElements** 및 **DestructElements** 사용 되지 않습니다.  
  
 Microsoft Foundation Class 라이브러리는 다음 전역 함수를 컬렉션 클래스를 사용자 지정할 수 있도록 afxtempl.h에 제공 합니다.  
  
### <a name="collection-class-helpers"></a>컬렉션 클래스 도우미  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|요소가 같은지 여부를 나타냅니다.|  
|[CopyElements](#copyelements)|다른 배열에서 요소를 복사 합니다.|  
|[DumpElements](#dumpelements)|스트림 지향 진단 출력을 제공합니다.|  
|[HashKey](#hashkey)|해시 키를 계산합니다.|  
|[SerializeElements](#serializeelements)|저장 하거나 보관 파일에서 구성 요소를 검색 합니다.|  
  
##  <a name="compareelements"></a>CompareElements  
 직접 호출 [CList::Find] (#not_found.md #clist__find clist class.md 및 간접적으로 [cmap__lookup](cmap-class.md#lookup) 및 [cmap__operator &#91; &#93;](cmap-class.md#operator_at)합니다.  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 비교할 첫 번째 요소의 형식입니다.  
  
 `pElement1`  
 비교할 첫 번째 요소에 대 한 포인터입니다.  
  
 `ARG_TYPE`  
 비교할 두 번째 요소의 형식입니다.  
  
 `pElement2`  
 비교할 두 번째 요소에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 가 가리키는 개체가 0이 아닌 `pElement1` 가 가리키는 개체가 같은지를 `pElement2`그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `CMap` 사용 하 여 호출 된 `CMap` 템플릿 매개 변수 *키* 및 `ARG_KEY`합니다.  
  
 비교의 결과 반환 하는 기본 구현은  *\*pElement1* 및  *\*pElement2*합니다. 응용 프로그램에 적합 한 방식으로 요소를 비교 하 여 되도록이 함수를 재정의 합니다.  
  
 비교 연산자를 정의 하는 c + + 언어 ( `==`) 단순 형식 ( `char`, `int`, **float**등) 되지만 클래스와 구조체에 대 한 비교 연산자를 정의 하지 않습니다. 사용 하려는 경우 `CompareElements` 를 사용 하는 컬렉션 클래스 중 하나를 인스턴스화할 때 비교 연산자를 정의 하거나 오버 로드 또는 `CompareElements` 버전은 적절 한 값을 반환 합니다.  
  
### <a name="requirements"></a>요구 사항  
   **헤더:** afxtempl.h   
  
##  <a name="copyelements"></a>CopyElements  
 이 함수를 직접 호출 [CArray::Append](carray-class.md#append) 및 [CArray::Copy](carray-class.md#copy)합니다.  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 복사할 요소 유형을 지정 하는 템플릿 매개 변수  
  
 `pDest`  
 요소가 복사 되는 대상에 대 한 포인터입니다.  
  
 `pSrc`  
 복사할 요소 소스에 대 한 포인터입니다.  
  
 `nCount`  
 복사할 요소의 수입니다.  
  
### <a name="remarks"></a>설명  
 단순 할당 연산자를 사용 하는 기본 구현 (  **=**  ) 복사 작업을 수행 합니다. 복사 하는 형식에 오버 로드 된 연산자가 없는 경우 =, 기본 구현은 비트 복사를 수행 합니다.  
  
 이 및 다른 도우미 함수 구현에 대 한 내용은 문서 참조 [컬렉션: 형식이 안전한 컬렉션을 만드는 방법](../how-to-make-a-type-safe-collection.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxtempl.h  
  
##  <a name="dumpelements"></a>DumpElements  
 재정의 된 경우 컬렉션의 요소에 대 한 텍스트 형식으로 스트림 지향 진단 출력을 제공 합니다.  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>매개 변수  
 `dc`  
 요소를 덤프 하기 위해 컨텍스트를 덤프 합니다.  
  
 *형식*  
 요소 유형을 지정 하는 템플릿 매개 변수  
  
 `pElements`  
 요소를 덤프할 수에 대 한 포인터입니다.  
  
 `nCount`  
 덤프할 수 있는 요소의 수입니다.  
  
### <a name="remarks"></a>설명  
 **CArray::Dump**, **CList::Dump**, 및 **CMap::Dump** 덤프의 깊이 0 보다 큰 경우이 함수 호출 합니다.  
  
 기본 구현은 아무 작업도 수행하지 않습니다. 컬렉션의 요소에서 파생 된 경우 `CObject`, 재정의 일반적으로 컬렉션의 요소를 반복 호출 `Dump` 선반에 있는 각 요소에 대 한 합니다.  
  

### <a name="requirements"></a>요구 사항  
  **헤더** afxtempl.h  
  
##  <a name="hashkey"></a>HashKey  
 지정된 된 키에 대 한 해시 값을 계산합니다.  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>매개 변수  
 `ARG_KEY`  
 맵 키에 액세스 하는 데 사용 하는 데이터 형식을 지정 하는 템플릿 매개 변수  
  
 `key`  
 해시 값을 계산 하는 키입니다.  
  
### <a name="return-value"></a>반환 값  
 키의 해시 값입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 직접 호출 [CMap::RemoveKey](cmap-class.md#removekey) 및 간접적으로 [CMap::Lookup](cmap-class.md#lookup) 및 [CMap::Operator &#91; &#93;](cmap-class.md#operator_at)합니다.
  
 기본 구현은 이동 하 여 해시 값을 만들고 `key` 네 위치 오른쪽으로 합니다. 응용 프로그램에 대 한 적절 한 해시 값을 반환이 함수를 재정의 합니다.  
  
### <a name="example"></a>예
 ```cpp  
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number 
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
 ```
 
### <a name="requirements"></a>요구 사항  
  **헤더** afxtempl.h 
  
##  <a name="serializeelements"></a>SerializeElements  
 [CArray](carray-class.md), [CList](clist-class.md), 및 [CMap](cmap-class.md) 요소를 serialize 하는 데이 함수를 호출 합니다.  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>매개 변수  
 *형식*  
 요소 유형을 지정 하는 템플릿 매개 변수  
  
 `ar`  
 보관 개체 간에 보관입니다.  
  
 `pElements`  
 보관 되 고 요소에 대 한 포인터입니다.  
  
 `nCount`  
 보관 되는 요소의 수  
  
### <a name="remarks"></a>설명  
 기본 구현은 그렇지 비트 읽기 또는 쓰기 합니다.  
  
 이 및 다른 도우미 함수 구현에 대 한 내용은 문서 참조 [컬렉션: 형식이 안전한 컬렉션을 만드는 방법](../how-to-make-a-type-safe-collection.md)합니다.  
  
### <a name="example"></a>예  
 예제 문서를 참조 하십시오 [컬렉션: 형식이 안전한 컬렉션을 만드는 방법](../how-to-make-a-type-safe-collection.md)합니다.  
 
### <a name="requirements"></a>요구 사항  
  **헤더** afxtempl.h 
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [CMap 클래스](cmap-class.md)   
 [CList 클래스](clist-class.md)   
 [CArray 클래스](carray-class.md)