---
title: CTypedPtrMap 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdb0c8679990a48740032017a2c0e11b7148f2d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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
 형식화 된 포인터 map 클래스;의 기본 클래스 포인터 맵 클래스 여야 합니다 ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, 또는 `CMapStringToPtr`).  
  
 `KEY`  
 맵에 대 한 키로 사용 되는 개체의 클래스입니다.  
  
 `VALUE`  
 Map에 저장 된 개체의 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|반복 하는 데 다음 요소를 가져옵니다.|  
|[CTypedPtrMap::Lookup](#lookup)|반환 된 `KEY` 기반으로 한 `VALUE`합니다.|  
|[CTypedPtrMap::RemoveKey](#removekey)|키가 지정 하는 요소를 제거 합니다.|  
|[CTypedPtrMap::SetAt](#setat)|map에 요소를 삽입 일치 하는 키가 있을 경우 기존 요소를 바꿉니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CTypedPtrMap::operator]](#operator_at)|지도 요소를 삽입 합니다.|  
  
## <a name="remarks"></a>설명  
 사용 하는 경우 `CTypedPtrMap`, c + + 형식 검사 기능에 일치 하지 않는 포인터 형식으로 인 한 오류를 제거 하는 데 도움이 됩니다.  
  
 때문에 모든 `CTypedPtrMap` 함수는 인라인, 크기 또는 코드의 속도이 템플릿을 사용 하 여 크게 적용 되지 않습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CTypedPtrMap`, 문서를 참조 [컬렉션](../../mfc/collections.md) 및 [템플릿 기반 클래스](../../mfc/template-based-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtempl.h  
  
##  <a name="getnextassoc"></a>  CTypedPtrMap::GetNextAssoc  
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
  
 *KEY*  
 Map의 키 유형을 지정 하는 템플릿 매개 변수  
  
 `rKey`  
 검색 된 요소의 반환 된 키를 지정합니다.  
  
 *값*  
 Map의 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `rValue`  
 검색 된 요소의 반환 된 값을 지정합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 map의 모든 요소를 통해 반복 하는 데 가장 유용 합니다. 참고 위치 시퀀스 아닌지 반드시 키 값 시퀀스와 동일 합니다.  
  
 검색된 된 요소는 맵에서 마지막 다음 새 값의 경우 `rNextPosition` 로 설정 된 **NULL**합니다.  
  
 이 인라인 함수가 호출 `BASE_CLASS` **:: GetNextAssoc**합니다.  
  
##  <a name="lookup"></a>  CTypedPtrMap::Lookup  
 `Lookup` 정확히 일치 하는 키가 있는 지도 요소를 빠르게 찾기 위해 해싱 알고리즘을 사용 합니다.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `BASE_CLASS`  
 이 맵의 클래스의 기본 클래스를 지정 하는 템플릿 매개 변수  
  
 `key`  
 조회 되는 요소의 키입니다.  
  
 *값*  
 이 맵에 저장 된 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `rValue`  
 검색 된 요소의 반환 된 값을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 발견 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 인라인 함수가 호출 `BASE_CLASS` **:: 조회**합니다.  
  
##  <a name="operator_at"></a>  CTypedPtrMap::operator]  
 이 연산자는 대입문 (l-value)의 왼쪽에만 사용할 수 있습니다.  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>매개 변수  
 *값*  
 이 맵에 저장 된 값의 형식을 지정 하는 템플릿 매개 변수  
  
 `BASE_CLASS`  
 이 맵의 클래스의 기본 클래스를 지정 하는 템플릿 매개 변수  
  
 `key`  
 조회 하거나 만들 맵에서 요소의 키입니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 키와 지도 요소가 경우 새 요소는 생성 됩니다. 없습니다 "오른쪽" (r-value)이이 운영자에 게 해당 되므로은 실패할 가능성이 있는 지도에서 키를 찾을 수 있습니다. 사용 하 여 `Lookup` 요소 검색에 대 한 멤버 함수입니다.  
  
##  <a name="removekey"></a>  CTypedPtrMap::RemoveKey  
 이 멤버 함수를 호출 `BASE_CLASS` **:: RemoveKey**합니다.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>매개 변수  
 *KEY*  
 Map의 키 유형을 지정 하는 템플릿 매개 변수  
  
 `key`  
 제거할 요소의 키입니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 찾아 제거 되었으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)합니다.  
  
##  <a name="setat"></a>  CTypedPtrMap::SetAt  
 이 멤버 함수를 호출 `BASE_CLASS` **:: SetAt**합니다.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>매개 변수  
 *KEY*  
 Map의 키 유형을 지정 하는 템플릿 매개 변수  
  
 `key`  
 새 값의 키 값을 지정합니다.  
  
 `newValue`  
 새 요소의 값에 해당 개체 포인터를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 설명에 자세한 참조 [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr 클래스](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord 클래스](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr 클래스](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr 클래스](../../mfc/reference/cmapstringtoptr-class.md)
