---
title: SafeInt 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce7715553e17e49ef3c169145abfb49816f6d6dd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="safeint-class"></a>SafeInt 클래스
기본 정수형을 확장하여 정수 오버플로를 방지하고 다양한 유형의 정수를 비교할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|템플릿|설명|  
|--------------|-----------------|  
|T|정수 또는 부울 타입의 `SafeInt` 가 대체하는 매개 변수 유형입니다.|  
|E|정책 처리 오류를 정의하는 열거형 데이터 형식입니다.|  
|U|정수 또는 보조 피연산자에 대 한 부울 매개 변수의 형식입니다.|  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] rhs|여러 독립 실행형 함수에 연산자의 오른쪽에 값을 나타내는 입력된 매개 변수|  
|[in] i|여러 독립 실행형 함수에 연산자의 오른쪽에 값을 나타내는 입력된 매개 변수|  
|[in] 비트|여러 독립 실행형 함수에 연산자의 오른쪽에 값을 나타내는 입력된 매개 변수|  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|기본 생성자입니다.|  
  
### <a name="assignment-operators"></a>할당 연산자  
  
|이름|구문|  
|----------|------------|  
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|  
|=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|  
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|  
|=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|  
  
### <a name="casting-operators"></a>캐스팅 연산자  
  
|이름|구문|  
|----------|------------|  
|bool|`operator bool() throw()`|  
|char|`operator char() const`|  
|signed char|`operator signed char() const`|  
|unsigned char|`operator unsigned char() const`|  
|__int16|`operator __int16() const`|  
|unsigned __int16|`operator unsigned __int16() const`|  
|__int32|`operator __int32() const`|  
|unsigned __int32|`operator unsigned __int32() const`|  
|long|`operator long() const`|  
|unsigned long|`operator unsigned long() const`|  
|__int64|`operator __int64() const`|  
|unsigned __int64|`operator unsigned __int64() const`|  
|wchar_t|`operator wchar_t() const`|  
  
### <a name="comparison-operators"></a>비교 연산자  
  
|이름|구문|  
|----------|------------|  
|<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|  
|<|`bool operator< (SafeInt<T,E> rhs) const throw()`|  
|>=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|  
|>=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|  
|>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|  
|>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|  
|<=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|  
|<=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|  
|==|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|  
|==|`bool operator== (bool rhs) const throw()`|  
|==|`bool operator== (SafeInt<T,E> rhs) const throw()`|  
|!=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|  
|!=|`bool operator!= (bool b) const throw()`|  
|!=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|  
  
### <a name="arithmetic-operators"></a>산술 연산자  
  
|이름|구문|  
|----------|------------|  
|+|`const SafeInt<T,E>& operator+ () const throw()`|  
|-|`SafeInt<T,E> operator- () const`|  
|++|`SafeInt<T,E>& operator++ ()`|  
|--|`SafeInt<T,E>& operator-- ()`|  
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|  
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|  
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|  
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|  
|*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|  
|*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|  
|*=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|  
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|  
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|  
|/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|  
|/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|  
|/=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|  
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|  
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|  
|+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|  
|+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|  
|+=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|  
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|  
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|  
|-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|  
|-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|  
|-=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|  
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|  
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|  
  
### <a name="logical-operators"></a>논리 연산자  
  
|이름|구문|  
|----------|------------|  
|!|`bool operator !() const throw()`|  
|~|`SafeInt<T,E> operator~ () const throw()`|  
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|  
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|  
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|  
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|  
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|  
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|  
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|  
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|  
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|  
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|  
|&=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|  
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|  
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|  
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|  
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|  
|^=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|  
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|  
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|  
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|  
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|  
|&#124;=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|  
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|  
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|  
  
## <a name="remarks"></a>설명  
 `SafeInt` 클래스는 수학 연산에서 정수 오버플로를 방지합니다. 예를 들어, 두 개의 8 비트 정수를 추가할 때, 첫 번째 값인 200과 두 번째 값인 100이 있을 때. 올바른 수학 연산에는 200 + 100 = 300일 것입니다. 그러나 8 비트 정수 제한으로 인해 상위 비트는 손실되고 컴파일러는 44를 반환 합니다(300-2<sup>8</sup>).  이 수학 방정식에 의존하는 모든 작업에 예기치 않은 동작이 수행됩니다.  
  
 `SafeInt` 클래스는 산술 오버플로가 발생하는지 여부와 코드가 0으로 나누려고 시도하는지 여부를 확인합니다. 두 경우 모두 클래스 프로그램의 잠재적 문제를 경고하는 오류 처리기를 호출합니다.
  
  
 `SafeInt` 개체라면 두 가지 다른 유형의 정수 간 비교가 가능합니다. 일반적으로 비교를 수행하는 경우 먼저 동일한 형식이 되도록 숫자를 변환해야 합니다. 다른 형식으로 숫자를 변환하는 것은 종종 그로 인한 데이터 손실 없이 있는지 확인하기 위한 검사가 필요합니다.  
  
 이 항목의 연산자 표에는 `SafeInt` 클래스가 지원하는 수치 연산 및 비교 연산자의 목록을 보여줍니다. 대부분 반환되는 수치 연산자는 `T` 형식의 `SafeInt` 개체입니다.  
  
 `SafeInt`와 정수 유형 간의 비교 연산은 방향과 관계 없이 수행할 수 있습니다. 예를 들어 `SafeInt<int>(x) < y`와 `y> SafeInt<int>(x)`는 유효하고 동일한 결과 반환합니다.  
  
 많은 이항 연산자는 두 가지의 다른 `SafeInt` 형식을 지원하지 않습니다. 대표적인 예가 `&` 연산자입니다.  `SafeInt<T, E> & int` 는 지원하지만 `SafeInt<T, E> & SafeInt<U, E>`는 지원하지 않습니다.  두 번째는 컴파일러가 어떤 유형의 매개 변수를 반환할지 알지 못합니다. 이 문제 해결 방법 중 하나는 두 번째 매개 변수를 기본 형식으로 다시 캐스팅하는 것 입니다. 동일한 매개 변수를 사용하면 `SafeInt<T, E> & (U)SafeInt<U, E>` 이렇게 가능합니다.  
  
> [!NOTE]
>  모든 비트 연산에 대한 두 개의 서로 다른 매개 변수 크기가 동일해야 합니다. 만일 크기가 다르다면, 컴파일러에서 [ASSERT](../mfc/reference/diagnostic-services.md#assert) 예외가 발생합니다. 이 동작에 대한 결과는 보장할 수 없습니다. 이 문제를 해결하려면 작은 매개 변수를 큰 크기의 매개 변수로 캐스팅합니다.  
  
 시프트 연산자의 경우 템플릿 형식보다 더 많은 비트를 시프트하면 ASSERT 예외가 발생합니다. 릴리스 모드에서는 아무런 영향을 주지 않습니다. 반환 형식은 원래 형식과 동일하기 때문에 두 가지 유형의 SafeInt 매개 변수를 혼합하는 것이 가능합니다. 연산자의 오른쪽에 있는 번호는 오직 이동할 비트 수를 나타냅니다.  
  
 SafeInt 개체 간 논리 비교를 수행하는 경우, 비교 동작은 엄격하게 계산됩니다. 예를 들어 다음 식을 참조하십시오.  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 첫 번째 문은 `true`로, 두 번째 문은 `false`로 풀이됩니다. 0에 대한 비트 부정은 0xFFFFFFFF입니다. 두 번째 문은 기본 비교 연산자 0xFFFFFFFF와 0xFFFFFFFF로 비교하고 동일한 것으로 간주합니다. `SafeInt` 클래스의 비교 연산자는 첫 번째 매개 변수를 부호가 없는 것으로, 두 번째 매개 변수를 음수로 인식합니다. 따라서 비트 표현은 동일하지만 `SafeInt` 논리 연산자는 부호 없는 정수가 -1보다 큰지 확인합니다.  
  
 `SafeInt`클래스를 `?:` 삼항 연산자와 함께 사용할 때 주의해야 합니다. 다음 코드 줄을 고려 합니다.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 컴파일러는 다음과 같이 변환합니다.   
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 `flag`가 `false`라면, 컴파일러는 `x`에 -1 값을 할당하는 대신 예외를 발생시킵니다. 따라서 이 문제를 방지하려면 다음과 같이 올바른 코드를 사용해야 합니다.
  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T` 및 `U`에는 부울 형식, 문자 형식이나 정수 형식을 지정할 수 있습니다. 정수 형식은 부호가 있을 수도 없을 수도 있고, 크기가 8비트에서 64비트까지 될 수 있습니다.  
  
> [!NOTE]
>  `SafeInt` 클래스는 모든 종류의 정수를 허용하지만, 부호 없는 형식이 보다 효율적으로 수행됩니다.  
  
 `E`는 `SafeInt`가 사용하는 오류 처리 메커니즘입니다. 두 오류 처리 메커니즘이 SafeInt 라이브러리에서 제공됩니다. 기본 정책은 `SafeIntErrorPolicy_SafeIntException` 이며, 오류가 발생하면 [SafeIntException 클래스](../windows/safeintexception-class.md) 예외가 발생합니다. 다른 정책은 오류 발생 시 프로그램을 중지하는 `SafeIntErrorPolicy_InvalidParameter`입니다.  
  
 오류 정책을 사용자 지정하는 방법은 두 가지가 있습니다. 첫 번째는 `E`를 만들 때 매개변수 `SafeInt`를 설정하는 것입니다. `SafeInt` 개체 하나의 오류 처리 정책 변경 시 이 방법을 사용합니다. 다른 방법은 `_SAFEINT_DEFAULT_ERROR_POLICY` 라이브러리를 포함하기 전에 `SafeInt`를 사용자 정의 오류 처리 클래스로 지정하는 것입니다. 코드에 사용된 모든 `SafeInt` 클래스 인스턴스의 기본 오류 처리 정책을 변경하려면 이 방법을 사용하십시오.  
  
> [!NOTE]
>  SafeInt 라이브러리에서 발생하는 오류를 처리하는 사용자 지정 클래스는 오류 처리기를 호출한 모드에 제어를 반환하지 않아야 합니다. 오류 처리기가 호출된 이후에는 `SafeInt` 연산 결과를 신뢰할 수 없습니다.   
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)