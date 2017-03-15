---
title: "&lt;system_error&gt; 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 82f7876aca66524ba50b1e01b74437d8a2117976
ms.lasthandoff: 02/24/2017

---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt; 연산자
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&lt;](#operator_lt_)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.  
  
```
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|같은지 테스트할 개체입니다.|  
|`right`|같은지 테스트할 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 개체가 같으면 **true**이고, 개체가 같지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `left.category() == right.category() && left.value() == right.value()`를 반환합니다.  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.  
  
```
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|같지 않은지 테스트할 개체입니다.|  
|`right`|같지 않은지 테스트할 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 `left`에서 전달된 개체가 `right`에서 전달된 개체와 같지 않으면 **true**이고, 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 함수는 `!(left == right)`를 반환합니다.  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 개체가 비교를 위해 전달된 개체보다 작은지 여부를 테스트합니다.  
  
```
template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|비교할 개체입니다.|  
|`right`|비교할 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 `left`에서 전달된 개체가 `right`에서 전달된 개체보다 작으면 **true**이고, 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 오류 순서를 테스트합니다.  
  
## <a name="see-also"></a>참고 항목  
 [<system_error>](../standard-library/system-error.md)




