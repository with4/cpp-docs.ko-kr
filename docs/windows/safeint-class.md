---
title: "SafeInt 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeInt
dev_langs: C++
helpviewer_keywords: SafeInt class
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: a031176d6636aedddbeac28c858c777c26625f5a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="safeint-class"></a>SafeInt 클래스
정수 오버플로 방지 하는 정수 기본 형식을 확장 하 고 다양 한 유형의 정수를 비교할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|템플릿|설명|  
|--------------|-----------------|  
|T|정수 또는 부울 매개 변수 유형의 `SafeInt` 대체 합니다.|  
|E|정책 처리 오류를 정의 하는 열거형된 데이터 형식입니다.|  
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
 `SafeInt` 클래스 수학 연산에서 정수 오버플로 방지 합니다. 예를 들어, 두 개의 8 비트 정수를 추가: 200 값이 하나이 고 두 번째 100의 값이 있습니다. 올바른 수학 연산에는 200 + 100 = 300 것입니다. 그러나 8 비트 정수 제한으로 인해 상위 비트를 손실 되 고 컴파일러 44를 반환 합니다 (300-2<sup>8</sup>)로 인해 합니다. 이 수학 방정식에 의존 하는 모든 작업에 예기치 않은 동작이 생성 됩니다.  
  
 `SafeInt` 클래스 산술 오버플로가 발생 하는지 여부 또는 코드 0으로 나누기 하려고 시도 하는지 여부를 확인 합니다. 두 경우 모두 클래스 프로그램의 잠재적 문제를 경고 하는 오류 처리기를 호출 합니다.  
  
 이 클래스 수도 있습니다는 두 가지 유형의 정수 비교 `SafeInt` 개체입니다. 일반적으로 비교를 수행 하는 경우 먼저 변환 해야 동일한 형식이 되도록 숫자입니다. 다른 형식으로 한 숫자를 종종 캐스팅 데이터 손실 없이 있는지 확인 하기 위해 검사 필요 합니다.  
  
 이 항목의 연산자 표에서 지 원하는 수치 연산 및 비교 연산자는 `SafeInt` 클래스입니다. 반환할 가장 수치 연산자는 `SafeInt` 형식의 개체 `T`합니다.  
  
 간의 비교 작업을 `SafeInt` 하며 정수 계열 형식 두 방향에서 모두 수행할 수 있습니다. 예를 들어 모두 `SafeInt<int>(x) < y` 및 `y > SafeInt<int>(x)` 유효 하 고 동일한 결과 반환 합니다.  
  
 많은 이항 연산자는 두 가지를 사용 하 여를 지원 하지 않는 `SafeInt` 형식입니다. 한 가지 예로는 `&` 연산자입니다. `SafeInt<T, E> & int`지원 하지만 `SafeInt<T, E> & SafeInt<U, E>` 않습니다. 두 번째 예제에서 컴파일러는 어떤 유형의 매개 변수를 반환할를 알지 못합니다. 이 문제 해결 방법 중 하나를 두 번째 매개 변수는 기본 형식으로 다시 캐스팅 되려고 합니다. 동일한 매개 변수를 사용 하 여 이렇게와 `SafeInt<T, E> & (U)SafeInt<U, E>`합니다.  
  
> [!NOTE]
>  모든 비트 연산을 대 한 두 개의 서로 다른 매개 변수 크기가 동일 해야 합니다. 크기가 다른 컴파일러에서 throw 한 [ASSERT](../mfc/reference/diagnostic-services.md#assert) 예외입니다. 정확 하 게이 작업의 결과 보장할 수 없습니다. 이 문제를 해결 하려면 더 큰 매개 변수 크기가 될 때까지 작은 매개 변수를 캐스팅 합니다.  
  
 시프트 연산자에 대 한 템플릿 형식에 대 한 보다 자세한 비트를 시프트 ASSERT 예외가 throw 됩니다. 릴리스 모드에서 아무런 영향을 주지를 갖습니다. 반환 형식을 원래 형식으로 동일 하기 때문에 두 가지 유형의 SafeInt 매개 변수를 혼합 하는 것이 시프트 연산자 가능 합니다. 연산자의 오른쪽에 있는 번호만 이동할 비트 수를 나타냅니다.  
  
 SafeInt 개체와 논리 비교를 수행 하는 경우 비교는 산술 엄격 하 게 합니다. 예, 이러한 식을 참조 하십시오.  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 첫 번째 문은 확인 `true`, 두 번째 문은로 확인 되지만 `false`합니다. 비트 부정 0은 0xFFFFFFFF입니다. 두 번째 문은 기본 비교 연산자는 0xFFFFFFFF 0xFFFFFFFF로 비교 하 고 동일한 것으로 간주 합니다. 에 대 한 비교 연산자는 `SafeInt` 클래스 첫 번째 매개 변수 서명 되지 않은 반면 두 번째 매개 변수가 음수 임을 인식 합니다. 따라서 비트 표현은 동일 하지만는 `SafeInt` 논리 연산자는 부호 없는 정수는-1 보다 큰 인식 합니다.  
  
 사용 하는 경우 주의 해야는 `SafeInt` 와 함께 클래스는 `?:` 삼항 연산자입니다. 다음 코드 줄을 고려 합니다.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 컴파일러가이으로 변환합니다.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 경우 `flag` 은 `false`,-1 값을 할당 하는 대신 예외를 throw 하는 컴파일러 `x`합니다. 따라서이 문제를 방지 하려면 올바른 코드를 사용 하는 다음 줄입니다.  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T`및 `U` 부울 형식, 문자 형식 또는 정수 형식에 할당할 수 있습니다. 정수 형식을 signed / unsigned 수 및 8 비트에서 64 비트로 모든 크기입니다.  
  
> [!NOTE]
>  하지만 `SafeInt` 클래스 허용 모든 종류의 정수, 부호 없는 형식으로 보다 효율적으로 수행 합니다.  
  
 `E`오류 처리 메커니즘은는 `SafeInt` 사용 합니다. 두 오류 처리 메커니즘은 SafeInt 라이브러리와 함께 제공 됩니다. 기본 정책은 `SafeIntErrorPolicy_SafeIntException`, throw 하는 [SafeIntException 클래스](../windows/safeintexception-class.md) 오류가 발생 하는 동안 예외가 발생 했습니다. 다른 정책을 `SafeIntErrorPolicy_InvalidParameter`, 오류가 발생 하면 프로그램을 중지 합니다.  
  
 오류 정책을 사용자 지정 하는 방법은 두 가지가 있습니다. 매개 변수를 설정 하는 첫 번째 옵션 `E` 만들 때 한 `SafeInt`합니다. 오류 처리 하나에 대 한 정책 변경 하려는 경우이 옵션을 사용 하 여 `SafeInt`합니다. 정의 하는 다른 옵션은 `_SAFEINT_DEFAULT_ERROR_POLICY` 오류 처리 사용자 지정 된 클래스를 포함 하기 전에 `SafeInt` 라이브러리입니다. 기본 오류 처리의 모든 인스턴스에 대 한 정책 변경 하려는 경우이 옵션을 사용 하 여는 `SafeInt` 코드의 클래스.  
  
> [!NOTE]
>  SafeInt 라이브러리에서 오류를 처리 하는 사용자 지정 된 클래스를 오류 처리기를 호출한 코드에 제어를 반환 해야 합니다. 오류 처리기가 호출의 결과 `SafeInt` 작업 신뢰할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)