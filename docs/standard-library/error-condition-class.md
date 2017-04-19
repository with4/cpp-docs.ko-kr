---
title: "error_condition 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_condition
- error_condition
- system_error/std::error_condition::value_type
- system_error/std::error_condition::assign
- system_error/std::error_condition::category
- system_error/std::error_condition::clear
- system_error/std::error_condition::message
- system_error/std::error_condition::operator bool
dev_langs:
- C++
helpviewer_keywords:
- error_condition class
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 4b9bc9b48c09c2b50b25eeb71a7fe9b5ad812157
ms.lasthandoff: 02/24/2017

---
# <a name="errorcondition-class"></a>error_condition 클래스
사용자 정의 오류 코드를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
class error_condition;
```  
  
## <a name="remarks"></a>설명  
 형식 `error_condition`의 개체는 오류 코드 값 및 보고된 사용자 정의 오류에 사용된 오류 코드의 [category](../standard-library/error-category-class.md)를 나타내는 개체에 대한 포인터를 저장합니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[error_condition](#error_condition__error_condition)|`error_condition` 형식의 개체를 생성합니다.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#error_condition__value_type)|저장된 오류 코드 값을 나타내는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[assign](#error_condition__assign)|오류 코드 값과 범주를 오류 조건에 할당합니다.|  
|[category](#error_condition__category)|오류 범주를 반환합니다.|  
|[clear](#error_condition__clear)|오류 코드 값과 범주를 지웁니다.|  
|[message](#error_condition__message)|오류 코드의 이름을 반환합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator==](#error_condition__operator_eq_eq)|`error_condition` 개체가 같은지 테스트합니다.|  
|[operator!=](#error_condition__operator_neq)|`error_condition` 개체가 같지 않은지 테스트합니다.|  
|[operator<](#error_condition__operator_lt_)|`error_condition` 개체가 비교를 위해 전달된 `error_code` 개체보다 작은지 테스트합니다.|  
|[operator=](#error_condition__operator_eq)|새 열거형 값을 `error_condition` 개체에 할당합니다.|  
|[operator bool](#error_condition__operator_bool)|형식 `error_condition`의 변수를 캐스트합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<system_error>  
  
 **네임스페이스:** std  
  
##  <a name="error_condition__assign"></a>  error_condition::assign  
 오류 코드 값과 범주를 오류 조건에 할당합니다.  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`val`|`error_code`에 저장할 오류 코드 값입니다.|  
|`_Cat`|`error_code`에 저장할 오류 범주입니다.|  
  
### <a name="remarks"></a>설명  
 멤버 함수는 `val`을 오류 코드 값 및 `_Cat`에 대한 포인터로 저장합니다.  
  
##  <a name="error_condition__category"></a>  error_condition::category  
 오류 범주를 반환합니다.  
  
```
const error_category& category() const;
```  
  
### <a name="return-value"></a>반환 값  
 저장된 오류 범주에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="error_condition__clear"></a>  error_condition::clear  
 오류 코드 값과 범주를 지웁니다.  
  
```
clear();
```  
  
### <a name="remarks"></a>설명  
 멤버 함수는&0; 오류 코드 값 및 [generic_category](../standard-library/system-error-functions.md#generic_category) 개체에 대한 포인터를 저장합니다.  
  
##  <a name="error_condition__error_condition"></a>  error_condition::error_condition  
 `error_condition` 형식의 개체를 생성합니다.  
  
```
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`val`|`error_condition`에 저장할 오류 코드 값입니다.|  
|`_Cat`|`error_condition`에 저장할 오류 범주입니다.|  
|`_Errcode`|`error_condition`에 저장할 열거형 값입니다.|  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는&0; 오류 코드 값 및 [generic_category](../standard-library/system-error-functions.md#generic_category)에 대한 포인터를 저장합니다.  
  
 두 번째 생성자는 `val`을 오류 코드 값 및 [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8)에 대한 포인터로 저장합니다.  
  
 세 번째 생성자는 `(value_type)_Errcode`를 오류 코드 값 및 [generic_category](../standard-library/system-error-functions.md#generic_category)에 대한 포인터로 저장합니다.  
  
##  <a name="error_condition__message"></a>  error_condition::message  
 오류 코드의 이름을 반환합니다.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>반환 값  
 오류 코드의 이름을 나타내는 `string`입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 `category().message(value())`를 반환합니다.  
  
##  <a name="error_condition__operator_eq_eq"></a>  error_condition::operator==  
 `error_condition` 개체가 같은지 테스트합니다.  
  
```
bool operator==(const error_condition& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`right`|같은지 테스트할 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 개체가 같으면 **true**이고, 개체가 같지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 멤버 연산자는 `category() == right.category() && value == right.value()`를 반환합니다.  
  
##  <a name="error_condition__operator_neq"></a>  error_condition::operator!=  
 `error_condition` 개체가 같지 않은지 테스트합니다.  
  
```
bool operator!=(const error_condition& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`right`|같지 않은지 테스트할 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 `error_condition` 개체가 `right`에 전달된 `error_condition` 개체와 같지 않으면 **true**이고, 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 멤버 연산자는 `!(*this == right)`를 반환합니다.  
  
##  <a name="error_condition__operator_lt_"></a>  error_condition::operator&lt;  
 `error_condition` 개체가 비교를 위해 전달된 `error_code` 개체보다 작은지 테스트합니다.  
  
```
bool operator<(const error_condition& right) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`right`|비교할 `error_condition` 개체입니다.|  
  
### <a name="return-value"></a>반환 값  
 `error_condition` 개체가 비교를 위해 전달된 `error_condition` 개체보다 작으면 **true**이고, 그렇지 않으면 **false**입니다.  
  
### <a name="remarks"></a>설명  
 멤버 연산자는 `category() < right.category() || category() == right.category() && value < right.value()`를 반환합니다.  
  
##  <a name="error_condition__operator_eq"></a>  error_condition::operator=  
 새 열거형 값을 `error_condition` 개체에 할당합니다.  
  
```
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
 operator=(Enum _Errcode);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Errcode`|`error_condition` 개체에 할당할 열거형 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 멤버 함수를 통해 새 열거형 값이 할당될 `error_condition` 개체에 대한 참조입니다.  
  
### <a name="remarks"></a>설명  
 멤버 연산자는 `(value_type)error`를 오류 코드 값 및 [generic_category](../standard-library/system-error-functions.md#generic_category)에 대한 포인터로 저장합니다. `*this`를 반환합니다.  
  
##  <a name="error_condition__operator_bool"></a>  error_condition::operator bool  
 형식 `error_condition`의 변수를 캐스트합니다.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>반환 값  
 `error_condition` 개체의 부울 값입니다.  
  
### <a name="remarks"></a>설명  
 연산자는 [value](#error_condition__value)가&0;과 같지 않을 경우에만 `true`로 변환할 수 있는 값을 반환합니다. 반환 형식은 `bool`로만 변환할 수 있고, `void *` 또는 기타 알려진 스칼라 형식으로 변환할 수 없습니다.  
  
##  <a name="error_condition__value"></a>  error_condition::value  
 저장된 오류 코드 값을 반환합니다.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>반환 값  
 형식 [value_type](#error_condition__value_type)의 저장된 오류 코드 값입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="error_condition__value_type"></a>  error_condition::value_type  
 저장된 오류 코드 값을 나타내는 형식입니다.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>설명  
 이 형식 정의는 `int`의 동의어입니다.  
  
## <a name="see-also"></a>참고 항목  
 [error_category 클래스](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)




