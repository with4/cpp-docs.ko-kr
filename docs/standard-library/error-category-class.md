---
title: "error_category 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
dev_langs:
- C++
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3befee5318756471e0eee6b975bdfb65f61c0391
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="errorcategory-class"></a>error_category 클래스
오류 코드 범주를 설명하는 개체에 대한 추상, 공통 기본을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
class error_category;
```  
  
## <a name="remarks"></a>설명  
 미리 정의된 두 개의 [generic_category](../standard-library/system-error-functions.md#generic_category) 및 [system_category](../standard-library/system-error-functions.md#system_category) 개체가 `error_category`를 구현합니다.  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[value_type](#value_type)|저장된 오류 코드 값을 나타내는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[default_error_condition](#default_error_condition)|오류 조건 개체에 대한 오류 코드 값을 저장합니다.|  
|[equivalent](#equivalent)|오류 개체가 동일한지 여부를 지정하는 값을 반환합니다.|  
|[message](#message)|지정된 오류 코드의 이름을 반환합니다.|  
|[name](#name)|범주 이름을 반환합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator==](#op_eq_eq)|`error_category` 개체가 같은지 테스트합니다.|  
|[operator!=](#op_neq)|`error_category` 개체가 같지 않은지 테스트합니다.|  
|[operator<](#op_lt)|[error_category](../standard-library/error-category-class.md) 개체가 비교를 위해 전달된 `error_category` 개체보다 작은지 테스트합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<system_error>  
  
 **네임스페이스:** std  
  
##  <a name="default_error_condition"></a>  error_category::default_error_condition  
 오류 조건 개체에 대한 오류 코드 값을 저장합니다.  
  
```
virtual error_condition default_error_condition(int _Errval) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Errval`|[error_condition](../standard-library/error-condition-class.md)에 저장할 오류 코드 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 `error_condition(_Errval, *this)`를 반환합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="equivalent"></a>  error_category::equivalent  
 오류 개체가 동일한지 여부를 지정하는 값을 반환합니다.  
  
```
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Errval`|비교할 오류 코드 값입니다.|  
|`_Cond`|비교할 [error_condition](../standard-library/error-condition-class.md) 개체입니다.|  
|`_Code`|비교할 [error_code](../standard-library/error-code-class.md) 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 범주와 값이 같으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 멤버 함수는 `*this == _Cond.category() && _Cond.value() == _Errval`을 반환합니다.  
  
 두 번째 멤버 함수는 `*this == _Code.category() && _Code.value() == _Errval`을 반환합니다.  
  
##  <a name="message"></a>  error_category::message  
 지정된 오류 코드의 이름을 반환합니다.  
  
```
virtual string message(error_code::value_type val) const = 0;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`val`|설명할 오류 코드 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 범주에 대한 오류 코드 `val`의 설명이 포함된 이름을 반환합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="name"></a>  error_category::name  
 범주 이름을 반환합니다.  
  
```
virtual const char *name() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 범주 이름을 null 종료 바이트 문자열로 반환합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="op_eq_eq"></a>  error_category::operator==  
 `error_category` 개체가 같은지 테스트합니다.  
  
```
bool operator==(const error_category& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`right`|같은지 테스트할 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 개체가 같으면 **true**이고, 개체가 같지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 연산자는 `this == &right`를 반환합니다.  
  
##  <a name="op_neq"></a>  error_category::operator!=  
 `error_category` 개체가 같지 않은지 테스트합니다.  
  
```
bool operator!=(const error_category& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`right`|같지 않은지 테스트할 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 `error_category` 개체가 `right`에 전달된 `error_category` 개체와 같지 않으면 **true**이고, 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 멤버 연산자는 `(!*this == right)`을 반환합니다.  
  
##  <a name="op_lt"></a>  error_category::operator&lt;  
 [error_category](../standard-library/error-category-class.md) 개체가 비교를 위해 전달된 `error_category` 개체보다 작은지 테스트합니다.  
  
```
bool operator<(const error_category& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`right`|비교할 `error_category` 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 `error_category` 개체가 비교를 위해 전달된 `error_category` 개체보다 작으면 **true**이고, 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 멤버 연산자는 `this < &right`을 반환합니다.  
  
##  <a name="value_type"></a>  error_category::value_type  
 저장된 오류 코드 값을 나타내는 형식입니다.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>설명  
 이 형식 정의는 `int`의 동의어입니다.  
  
## <a name="see-also"></a>참고 항목  
 [<system_error>](../standard-library/system-error.md)



