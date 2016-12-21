---
title: "SafeInt 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt 클래스"
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
caps.latest.revision: 16
caps.handback.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeInt 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정수 오버 플로우를 방지하고 당신이 정수의 다른 유형을 비교하고 돕기 위하여 정수의 기본을 확장합니다.  
  
## 구문  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### 매개 변수  
  
|템플릿|설명|  
|---------|--------|  
|T|`SafeInt`  대체하는 부울 매개변수 또는 정수의 유형.|  
|E|오류 처리 정책을 정의하는 열거형된 데이터 형식입니다.|  
|U|보조 피연산자에 대한 정수 또는 부울 매개 변수의 형식입니다.|  
  
|Parameter|설명|  
|---------------|--------|  
|\[in\] rhs|몇개의 독립 기능의 연산자 오른쪽 값을 나타내는 입력 매개변수입니다.|  
|\[in\] i|몇개의 독립 기능의 연산자 오른쪽 값을 나타내는 입력 매개변수입니다.|  
|\[in\] bits|몇개의 독립 기능의 연산자 오른쪽 값을 나타내는 입력 매개변수입니다.|  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|기본 생성자입니다.|  
  
### 할당 연산자  
  
|Name|구문|  
|----------|--------|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|  
  
### 캐스팅 연산자  
  
|Name|구문|  
|----------|--------|  
|bool|`operator bool() throw()`|  
|char|`operator char() const`|  
|signed char|`operator signed char() const`|  
|unsigned char|`operator unsigned char() const`|  
|\_\_int16|`operator __int16() const`|  
|unsigned \_\_int16|`operator unsigned __int16() const`|  
|\_\_int32|`operator __int32() const`|  
|unsigned \_\_int32|`operator unsigned __int32() const`|  
|long|`operator long() const`|  
|unsigned long|`operator unsigned long() const`|  
|\_\_int64|`operator __int64() const`|  
|unsigned \_\_int64|`operator unsigned __int64() const`|  
|wchar\_t|`operator wchar_t() const`|  
  
### 비교 연산자  
  
|Name|구문|  
|----------|--------|  
|\<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|  
|\<|`bool operator< (SafeInt<T,E> rhs) const throw()`|  
|\>\=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|  
|\>\=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|  
|\>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|  
|\>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|  
|\<\=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|  
|\<\=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|  
|\=\=|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|  
|\=\=|`bool operator== (bool rhs) const throw()`|  
|\=\=|`bool operator== (SafeInt<T,E> rhs) const throw()`|  
|\!\=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|  
|\!\=|`bool operator!= (bool b) const throw()`|  
|\!\=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|  
  
### 산술 연산자  
  
|Name|구문|  
|----------|--------|  
|\+|`const SafeInt<T,E>& operator+ () const throw()`|  
|\-|`SafeInt<T,E> operator- () const`|  
|\+\+|`SafeInt<T,E>& operator++ ()`|  
|\-\-|`SafeInt<T,E>& operator-- ()`|  
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|  
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|  
|\*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|  
|\*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|  
|\*\=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|  
|\/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|  
|\/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|  
|\/\=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|  
|\+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|  
|\+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|  
|\+\=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|  
|\-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|  
|\-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|  
|\-\=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|  
  
### 논리 연산자  
  
|Name|구문|  
|----------|--------|  
|\!|`bool operator !() const throw()`|  
|~|`SafeInt<T,E> operator~ () const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|  
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|  
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|  
|&\=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|  
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|  
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|  
|^\=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|  
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|  
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|  
|&#124;\=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|  
  
## 설명  
 `SafeInt`  클래스는 수학 연산에서 정수 오버플로를 방지합니다.  예를 들어, 두 개의 8 비트 정수를 추가합니다: 하나는 200의 값을 갖고 두 번째는 100을 갖습니다.  올바른 수학 연산은   200 \+ 100 \= 300 입니다.  그러나, 8 비트 정수 제한 때문에 상위 비트가 손실되고 컴파일러는 44 \(300\-2<sup>8</sup>\)를 결과로 반환합니다.  이 수학 방정식에 종속된 작업에는 예기치 않은 동작이 발생합니다.  
  
 `SafeInt`  클래스는 산술 오버플로가 발생 하는 여부 또는 코드 0으로 나누려고 시도하는 여부를 확인합니다.  두 경우 모두 클래스는 프로그램의 잠재적인 문제를 경고하는 오류 처리기를 호출합니다.  
  
 이 클래스는   `SafeInt`  개체 그대로의 정수의 두 가지 유형을 비교할 수 있습니다.  비교를 수행 할 때 일반적으로 먼저 같은 유형으로 숫자를 변환해야합니다.  종종 한 숫자를 다른 형식 캐스팅 데이터가 손실 되지 않았는지 확인하기 위해 검사를 해야합니다.  
  
 이 항목의 연산자 테이블은 `SafeInt` 클래스에 의해 지원되는 수학 및 비교 연산자를 보여줍니다.  가장 수치 연산자는  `T`  형식의  `SafeInt`  개채를 반환합니다..  
  
 `SafeInt` 와 정수 형식 사이의 비교작업은 어느 한 방향으로 수행이 가능합니다.  예를 들어,  `SafeInt<int>(x) < y`  및  `y > SafeInt<int>(x)` 둘다 유효하고 같은 결과를 반환합니다.  
  
 2 진 연산자는 두 개의 서로 다른 `SafeInt` 유형을 사용하여 지원하지 않습니다.  이것의 한 예로  `&`  운영자가 있습니다.  `SafeInt<T, E> & int`는 지원 하지만  `SafeInt<T, E> & SafeInt<U, E>` 는 지원하지 않습니다.  두 번째 예제에서는 컴파일러가 반환하는 매개 변수의 형식을 알지 못합니다.  이 문제를 해결하는 한 가지 방법은 기본 형식으로 다시 두 번째 매개 변수를 캐스팅하는 것입니다.  동일한 매개 변수를 사용하여  `SafeInt<T, E> & (U)SafeInt<U, E>` 을 사용할 수 있습니다.  
  
> [!NOTE]
>  모든 비트 연산을 두 개의 다른 매개 변수는 동일한 크기여야 합니다.  크기가 다를 경우는 컴파일러가 [ASSERT](../Topic/ASSERT%20\(MFC\).md) 예외를 throw 합니다.  이 작업의 결과를 정확하게 보장할 수 없습니다.  이 문제를 해결 하려면 큰 매개 변수와 동일해질 때까지 작은 매개 변수를 캐스팅해야 합니다.  
  
 이동 통신 사업자의 경우, 템플릿 형식에 존재하는 것보다 더 많은 비트를 이동하면 ASSERT 예외가 발생합니다.  릴리스 모드에서 적용되지 않습니다.  반환 형식은 원래의 형식과 동일하기 때문에 SafeInt 매개 변수의 두 가지 유형을 혼합하면 이동 통신을 할 수 있습니다.  연산자 오른쪽 숫자는 시프트 비트 수를 나타낸다.  
  
 SafeInt 개체를 사용하여 논리 비교를 수행 할 때, 비교는 엄격하게 산술입니다.  예를 들어, 이 식을 고려해야 합니다.  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 첫 번째 문은  `true` 로 해결하지만, 두 번째 명령문은  `false` 로 해결합니다.  0의 비트 부정은 0xFFFFFFFF입니다.  두 번째 문에서 기본 비교 연산자는 0xFFFFFFFF 에 0xFFFFFFFF 을 비교하고는 동일한 것으로 간주합니다.   `SafeInt`  클래스에 대한 비교 연산자는 첫 번째 매개 변수는 서명되지 않은 반면, 두 번째 매개 변수가 음수임을 깨닫습니다.  따라서 비트 표시는 동일 하지만,  `SafeInt`  논리 연산자는 큰 부호 없는 정수를 \-1보다 크다고  인식합니다.  
  
 `SafeInt` 을  `?:`  삼항 연산자와 함께 사용할때 주의해야합니다.  다음 코드 줄을 살펴봅니다.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 컴파일러는 다음으로 변환합니다:  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 `flag`  가  `false` 일 경우, 컴파일러는 대신 `x`에 \-1의 값을 할당하는 예외를 throw합니다.  따라서,이 문제를 방지하기 위해 사용하는 올바른 코드는 다음과 라인입니다.  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T`및  `U` 는 부울 형식, 문자 형식 또는 정수 형식을 지정할 수 있습니다.  정수 타입은 서64 비트 부호없는 8 비트에서 어떤 크기를 서명하거나 서명을 취소할 수 있다.  
  
> [!NOTE]
>  하지만  `SafeInt`  클래스는 모든 종류의 정수를 받아들이지만, 부호 없는 형식을  보다 효율적으로 수행합니다.  
  
 `E`는  `SafeInt`  를 사용하는 메커니즘을 처리하는 오류입니다.  두 가지 오류 처리 메커니즘은 SafeInt 라이브러리에 포함되어 있습니다.  기본 정책은오류가 발생할 때 [SafeIntException 클래스](../windows/safeintexception-class.md) 예외를 throw하는  `SafeIntErrorPolicy_SafeIntException` 입니다.  다른 정책은 오류가 발생 하면 프로그램을 중지 하는  `SafeIntErrorPolicy_InvalidParameter` 입니다.  
  
 오류 정책을 사용자 지정하는 방법은 두 가지가 있습니다.  첫 번째 방법은  `SafeInt` 을 생성할 때  `E`  매개 변수를 설정하는 것입니다.   `SafeInt`  정책 하나에 대한 처리 오류를 변경하려면이 옵션을 사용합니다.  다른 옵션은 `_SAFEINT_DEFAULT_ERROR_POLICY` 을 정의하여 `SafeInt` 라이브러리를 포함하기 저에 오류 처리 클래스를 사용자지정하는 것입니다.  기본 오류 처리의 코드에서 모든  `SafeInt` 클래스의 인스턴스에 대한 정책을 변경 하려면 이 옵션을 사용하십시오.  
  
> [!NOTE]
>  SafeInt 라이브러리에서 오류를 처리하는 사용자 정의 클래스는 오류 처리기를 호출 한 코드로 제어를 반환하지 않아야합니다.  오류 처리기가 호출된 후,  `SafeInt`  작업의 결과는 신뢰할 수 없습니다.  
  
## 요구 사항  
 **헤더:** safeint.h  
  
 **네임 스페이스:** msl::utilities  
  
## 참고 항목  
 [Miscellaneous Support Libraries Classes](http://msdn.microsoft.com/ko-kr/406fd46e-d53f-4096-ab40-36aa754c7a5c)   
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)