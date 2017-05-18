---
title: "CTypedPtrMap 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections
- template classes, CTypedPtrMap class
- maps
- CTypedPtrMap class
- pointer maps
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 919d751c6ffe4b10ffad047f1b6be832bf49a1af
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap 클래스
`CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`및 `CMapStringToPtr`포인터-맵 클래스 개체에 대해 형식 안전 "래퍼"를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class BASE_CLASS, class KEY, class VALUE>  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>매개 변수  
 `BASE_CLASS`  
 형식화 된 포인터 map 클래스의 기본 클래스 포인터 맵 클래스 여야 합니다 ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, 또는 `CMapStringToPtr`).  
  
 `KEY`  
 지도 키로 사용 되는 개체의 클래스입니다.  
  
 `VALUE`  
 Map에 저장 하는 개체의 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CTypedPtrMap::Lookup](#lookup)|반환 된 `KEY` 기반으로 한 `VALUE`.|  
|[CTypedPtrMap::RemoveKey](#removekey)|키가 지정 된 요소를 제거 합니다.|  
|[CTypedPtrMap::SetAt](#setat)|Map에 요소를 삽입합니다. 일치 하는 키가 있을 경우에 기존 요소를 대체 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CTypedPtrMap::operator]](#operator_at)|Map에 요소를 삽입합니다.|  
  
## <a name="remarks"></a>주의  
 사용 하는 경우 `CTypedPtrMap`, c + + 형식 검사 기능에 짝이 맞지 않는 포인터 형식으로 인 한 오류를 제거 하는 데 도움이 됩니다.  
  
 때문에 모든 `CTypedPtrMap` 함수는 인라인, 크기 또는 코드의 속도이 템플릿을 사용 하 여 크게 적용 되지 않습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CTypedPtrMap`, 문서를 참조 [컬렉션](../../mfc/collections.md) 및 [템플릿 기반 클래스](../../mfc/template-based-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtempl.h  
  
##  <a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc  
 에 지도 요소를 검색 `rNextPosition`, 그런 다음 업데이트 `rNextPosition` 맵에서 다음 요소를 참조 하 합니다.  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `rPosition`  
 에 대 한 참조를 지정 된 **위치** 이전에서 반환 된 값 `GetNextAssoc` 또는 `BASE_CLASS` **:: GetStartPosition** 호출 합니다.  
  
 *키*  
 Map의 키 유형을 지정 하는 템플릿 매개 변수  
  
 `rKey`  
 검색 된 요소의 반환 된 키를 지정합니다.  
  
 *값*  
 Map의 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `rValue`  
 검색 된 요소의 반환 된 값을 지정합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 지도에 있는 모든 요소를 통해 반복 하는 데 가장 유용 합니다. 않음을 유의 하십시오 위치 시퀀스 반드시 키 값 시퀀스와 동일 합니다.  
  
 검색 된 요소가 있으면 지도 마지막 다음의 새 값 `rNextPosition` 로 설정 된 **NULL**합니다.  
  
 이 인라인 함수를 호출 `BASE_CLASS` **:: GetNextAssoc**합니다.  
  
##  <a name="lookup"></a>CTypedPtrMap::Lookup  
 `Lookup`해시 알고리즘을 사용 하 여 정확히 일치 하는 키가 있는 지도 요소를 빠르게 찾을.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `BASE_CLASS`  
 이 map 클래스의 기본 클래스를 지정 하는 템플릿 매개 변수  
  
 `key`  
 조회 되는 요소의 키입니다.  
  
 *값*  
 이 맵에 저장 된 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `rValue`  
 검색 된 요소의 반환 된 값을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 발견 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 인라인 함수를 호출 `BASE_CLASS` **:: 조회**합니다.  
  
##  <a name="operator_at"></a>CTypedPtrMap::operator]  
 이 연산자 (l-value) 대입문의 왼쪽에만 사용할 수 있습니다.  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>매개 변수  
 *값*  
 이 맵에 저장 된 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `BASE_CLASS`  
 이 map 클래스의 기본 클래스를 지정 하는 템플릿 매개 변수  
  
 `key`  
 키를 조회 하거나 맵에서 만들 요소입니다.  
  
### <a name="remarks"></a>주의  
 지정된 된 키와 지도 요소가 이면 새 요소가 만들어집니다. 경우 없습니다 "오른쪽" (r-value)이이 운영자에 해당 하는 지도에서 키를 찾을 수 있습니다 가능성이 있기 때문에 사용 하 여 `Lookup` 요소 검색을 위한 멤버 함수입니다.  
  
##  <a name="removekey"></a>CTypedPtrMap::RemoveKey  
 이 멤버 함수를 호출 `BASE_CLASS` **:: RemoveKey**합니다.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>매개 변수  
 *키*  
 Map의 키 유형을 지정 하는 템플릿 매개 변수  
  
 `key`  
 제거할 요소의 키입니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 찾아 성공적으로 제거 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 자세한 설명 부분 참조 [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)합니다.  
  
##  <a name="setat"></a>CTypedPtrMap::SetAt  
 이 멤버 함수를 호출 `BASE_CLASS` **:: SetAt**합니다.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>매개 변수  
 *키*  
 Map의 키 유형을 지정 하는 템플릿 매개 변수  
  
 `key`  
 새 값의 키 값을 지정합니다.  
  
 `newValue`  
 새 요소의 값은 개체 포인터를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 자세한 설명 부분 참조 [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플을 수집](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr 클래스](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord 클래스](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr 클래스](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr 클래스](../../mfc/reference/cmapstringtoptr-class.md)

