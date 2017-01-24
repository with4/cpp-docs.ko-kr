---
title: "&lt; 기능 &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<functional>"
  - "functional/std::<functional>"
  - "std.<functional>"
  - "std::<functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "functors"
  - "functional 헤더"
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; 기능 &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

생성 하는 데 도움이 되는 표준 라이브러리 함수를 정의 *개체 함수*-함수 라고도-및 해당 바인더입니다. 함수 개체는 `operator()`를 정의하는 형식의 개체입니다. 함수 개체는 함수 포인터일 수 있지만, 개체를 사용하여 함수 호출 중에 액세스할 수 있는 추가 정보를 저장하는 것이 더 일반적입니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <functional>  
```  
  
## <a name="remarks"></a>주의  
 알고리즘에는 단항 및 이항의 두 가지 함수 개체 형식이 필요합니다. 단항 함수 개체에는 인수가 하나 필요하고 이항 함수 개체에는 인수가 두 개 필요합니다. 함수 개체 및 함수 포인터는 알고리즘 조건자로 전달할 수 있지만 함수 개체는 조정 가능하며 STL의 범위, 유연성 및 효율성을 높입니다. 예를 들어 값이 알고리즘에 전달되기 전에 함수에 바인딩되어야 하는 경우 함수 포인터를 사용할 수 없습니다. 함수 어댑터는 함수 포인터를 값에 바인딩될 수 있는 조정 가능한 함수 개체로 변환합니다. 헤더 \< 기능> 멤버 함수를 융통성 있는 함수 개체를 호출할 수 있도록 하는 멤버 함수 어댑터도 포함 합니다. 함수는 해당 인수 및 반환 형식을 지정하는 중첩 형식 선언을 포함하는 경우 조정 가능합니다. C++ 표준에서는 모든 표준 개체 클래스가 unary_function 또는 binary_function 기본 클래스에서 상속하도록 하여 이 적응성을 구현해야 합니다. 함수 개체와 해당 어댑터는 STL이 기존 응용 프로그램을 업그레이드할 수 있도록 하며 STL을 C++ 프로그래밍 환경으로 통합하는 데 도움이 됩니다.  
  
  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 구현에 있는 함수 개체의 \< 기능> 포함 *투명 연산자 함수*, 표준의 특수화 된 함수 개체 및 템플릿 매개 변수를 하 고 수행 함수 인수의 완벽 한 전달 및 완벽 한 결과 반환 합니다. 이 기능은 C++14 초안 표준 사양의 일부입니다. 이러한 템플릿 특수화는 산술, 비교, 논리 및 비트 연산자 함수를 호출할 때 인수 형식을 지정할 필요가 없습니다. 사용자 고유의 형식 또는 다른 유형의 형식 조합에 대해 산술, 비교, 논리 또는 비트 연산자를 오버로드할 수 있으며 투명 연산자 함수를 함수 인수로 사용할 수 있습니다. 예를 들어 경우 형식이 *MyType* 구현 `operator<`, 를 호출할 수 있습니다 `sort(my_collection.begin(), my_collection.end(), less<>())` 명시적으로 형식을 지정 하는 대신 `sort(my_collection.begin(), my_collection.end(), less<MyType>())`합니다.  
  
## <a name="c11c14-implementation"></a>C++11/C++14 구현  
 C++11/C++14의 Visual C++ 구현에서 다음 기능이 추가되었습니다.  
  
-   A *호출 서명을* 이름 뒤에 0 개 이상의 인수 형식의 괄호로 묶인 쉼표로 구분 된 목록으로 반환 형식입니다.  
  
-   A *호출 가능 형식* 함수, 멤버 함수에 대 한 포인터, 멤버 데이터에 대 한 포인터 또는 함수 호출 연산자의 왼쪽에 해당 개체가 즉시 나타날 수 클래스 형식에 대 한 포인터입니다.  
  
-   A *호출 가능 개체* 는 호출 가능한 형식의 개체입니다.  
  
-   A *래퍼 형식을 호출할* 형식은 호출 가능 개체를 보유 하 고 해당 개체에 전달 하는 호출 작업을 지원 합니다.  
  
-   A *호출 래퍼* 는 호출 래퍼 형식의 개체입니다.  
  
-   A *대상 개체* 호출 래퍼 개체에서 보유 하는 호출 가능 개체입니다.  
  
 의사(pseudo) 함수 `INVOKE(f, t1, t2, ..., tN)`은 다음 중 하나를 의미합니다.  
  
- `f`가 `T` 클래스의 멤버 함수에 대한 포인터이고, `t1`이 `T` 형식의 개체이거나 `T` 형식의 개체에 대한 참조 또는 `T`에서 파생된 형식의 개체에 대한 참조인 경우 `(t1.*f)(t2, ..., tN)`입니다.  
  
- `f`가 `T` 클래스의 멤버 함수에 대한 포인터이고 `t1`이 이전 항목에서 설명한 형식 중 하나가 아닌 경우 `((*t1).*f)(t2, ..., tN)`입니다.  
  
- N == 1이며 `f`가 `T` 클래스의 멤버 데이터에 대한 포인터이고, `t1`이 `T` 형식의 개체이거나 `T` 형식의 개체에 대한 참조 또는 `T`에서 파생된 형식의 개체에 대한 참조인 경우 `t1.*f`입니다.  
  
- N == 1이며 `f`가 `T` 클래스의 멤버 데이터에 대한 포인터이고 `t1`이 이전 항목에서 설명한 형식 중 하나가 아닌 경우 `(*t1).*f`입니다.  
  
- 다른 모든 경우에서는 `f(t1, t2, ..., tN)`입니다.  
  
 의사(pseudo) 함수 `INVOKE(f, t1, t2, ..., tN, R)`은 `INVOKE(f, t1, t2, ..., tN)`이 `R`로 암시적으로 변환되었음을 의미합니다.  
  
 호출 래퍼에는 *강력 하지 않은 결과 형식을*, 해당 멤버의 형식 `result_type` 형식에 따라 `T` 다음과 같이 래퍼 대상 개체의:  
  
-   `T`가 함수에 대한 포인터인 경우 `result_type`은 `T`의 반환 형식에 대한 동의어입니다.  
  
-   `T`가 멤버 함수에 대한 포인터인 경우 `result_type`은 `T`의 반환 형식에 대한 동의어입니다.  
  
-   `T`가 멤버 형식 `result_type`을 포함하는 클래스 형식인 경우 `result_type`은 `T::result_type`에 대한 동의어입니다.  
  
-   그렇지 않은 경우 멤버 `result_type`이 없습니다.  
  
 각 호출 래퍼에 이동 생성자 및 복사 생성자가 있습니다. A *간단한 호출 래퍼* 호출 래퍼가 있는 대입 연산자 및 해당 복사 생성자, 이동 생성자와 대입 연산자 예외를 throw 하지 않습니다. A *호출 래퍼를 전달* 임의의 인수 목록을 사용 하 여 호출할 수 있는 호출 래퍼 이므로 인수는 래핑된 호출 가능 개체에 대 한 참조로 배달 하는 합니다. 모든 rvalue 인수는 rvalue 참조로 전달되고 lvalue 인수는 lvalue 참조로 전달됩니다.  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[bad_function_call](../standard-library/bad-function-call-class.md)|나타내기 위해 throw 된 예외에 대 한 호출을 설명 하는 클래스 `operator()` 에 [함수](../standard-library/function-class.md) 개체가 비어 있으므로 개체가 실패 했습니다.|  
|[binary_negate](../standard-library/binary-negate-class.md)|지정된 이항 함수의 반환 값을 부정하는 멤버 함수를 제공하는 템플릿 클래스입니다.|  
|[binder1st](../standard-library/binder1st-class.md)|이항 함수의 첫 번째 인수를 지정된 값에 바인딩하여 이항 함수 개체를 단항 함수 개체로 변환하는 생성자를 제공하는 템플릿 클래스입니다.|  
|[binder2nd](../standard-library/binder2nd-class.md)|이항 함수의 두 번째 인수를 지정된 값에 바인딩하여 이항 함수 개체를 단항 함수 개체로 변환하는 생성자를 제공하는 템플릿 클래스입니다.|  
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|참조 인수를 사용하여 초기화할 때 인수를 사용하지 않는 const 멤버 함수를 단항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다.|  
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|포인터 인수를 사용하여 초기화할 때 인수를 사용하지 않는 const 멤버 함수를 단항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다.|  
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|참조 인수를 사용하여 초기화할 때 단일 인수를 사용하는 const 멤버 함수를 이항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다.|  
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|포인터 인수를 사용하여 초기화할 때 단일 인수를 사용하는 const 멤버 함수를 이항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다.|  
|[함수](../standard-library/function-class.md)|호출 가능 개체를 래핑하는 클래스입니다.|  
|[해시](../standard-library/hash-class.md)|값에 대한 해시 코드를 계산하는 클래스입니다.|  
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|`bind`를 호출하여 특정 형식이 생성되었는지 테스트하는 클래스입니다.|  
|[is_placeholder](../standard-library/is-placeholder-class.md)|특정 형식이 자리 표시자인지 테스트하는 클래스입니다.|  
|[mem_fun_ref_t](../standard-library/mem-fun-ref-t-class.md)|허용 하는 어댑터 클래스는 **non_const** 인수는 참조를 사용 하 여 초기화 하는 경우에 단항 함수 개체를 호출할 수 없는 인수를 사용 하는 멤버 함수입니다.|  
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|허용 하는 어댑터 클래스는 **non_const** 멤버 함수는 인수가 없는 단항 함수 개체 포인터 인수를 사용 하 여 초기화 하는 경우으로 호출 합니다.|  
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|허용 하는 어댑터 클래스는 **non_const** 멤버 함수는 인수는 참조를 사용 하 여 초기화 하는 경우에 이진 함수 개체와 호출 되는 단일 인수를 사용 합니다.|  
|[mem_fun1_t](../standard-library/mem-fun1-t-class.md)|허용 하는 어댑터 클래스는 **non_const** 포인터 인수를 사용 하 여 초기화 하는 경우에 이진 함수 개체와 호출 되는 단일 인수를 사용 하는 멤버 함수입니다.|  
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|이항 함수 포인터를 조정 가능한 이항 함수로 변환합니다.|  
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|단항 함수 포인터를 조정 가능한 단항 함수로 변환합니다.|  
|[reference_wrapper](../standard-library/reference-wrapper-class.md)|참조를 래핑하는 클래스입니다.|  
|[result_of](../standard-library/result-of-class2.md)|래핑된 호출 가능 개체의 반환 형식을 보유하는 구조체입니다.|  
|[unary_negate](../standard-library/unary-negate-class.md)|지정된 단항 함수의 반환 값을 부정하는 멤버 함수를 제공하는 템플릿 클래스입니다.|  
  
### <a name="functions"></a>함수  
  
|||  
|-|-|  
|[바인딩](../Topic/%3Cfunctional%3E%20functions.md#bind_function)|호출 가능 개체에 인수를 바인딩합니다.|  
|[bind1st](../Topic/%3Cfunctional%3E%20functions.md#bind1st_function)|이항 함수의 첫 번째 인수를 지정된 값에 바인딩하여 이항 함수 개체를 단항 함수 개체로 변환하는 어댑터를 만드는 도우미 템플릿 함수입니다.|  
|[bind2nd](../Topic/%3Cfunctional%3E%20functions.md#bind2nd_function)|이항 함수의 두 번째 인수를 지정된 값에 바인딩하여 이항 함수 개체를 단항 함수 개체로 변환하는 어댑터를 만드는 도우미 템플릿 함수입니다.|  
|[bit_and](../Topic/%3Cfunctional%3E%20functions.md#bit_and_function)|두 매개 변수의 비트 논리적 AND(binary operator&)를 반환합니다.|  
|[bit_not](../Topic/%3Cfunctional%3E%20functions.md#bit_not_function)|매개 변수의 비트 논리적 보수(operator~)를 반환합니다.|  
|[bit_or](../Topic/%3Cfunctional%3E%20functions.md#bit_or_function)|비트 논리 OR 반환 (연산자 &#124;)의 두 매개 변수입니다.|  
|[bit_xor](../Topic/%3Cfunctional%3E%20functions.md#bit_xor_function)|두 매개 변수의 비트 논리적 XOR(operator^)을 반환합니다.|  
|[cref](../Topic/%3Cfunctional%3E%20functions.md#cref_function)|인수에서 const `reference_wrapper`를 생성합니다.|  
|[mem_fn](../Topic/%3Cfunctional%3E%20functions.md#mem_fn_function)|단순 호출 래퍼를 생성합니다.|  
|[mem_fun](../Topic/%3Cfunctional%3E%20functions.md#mem_fun_function)|포인터 인수를 사용하여 초기화할 때 멤버 함수에 대한 함수 개체 어댑터를 생성하는 데 사용되는 도우미 템플릿 함수입니다.|  
|[mem_fun_ref](../Topic/%3Cfunctional%3E%20functions.md#mem_fun_ref_function)|참조 인수를 사용하여 초기화할 때 멤버 함수에 대한 함수 개체 어댑터를 생성하는 데 사용되는 도우미 템플릿 함수입니다.|  
|[not1](../Topic/%3Cfunctional%3E%20functions.md#not1_function)|단항 조건자의 보수를 반환합니다.|  
|[not2](../Topic/%3Cfunctional%3E%20functions.md#not2_function)|이항 조건자의 보수를 반환합니다.|  
|[ptr_fun](../Topic/%3Cfunctional%3E%20functions.md#ptr_fun_function)|단항 및 이항 함수 포인터를 각각 조정 가능한 단항 및 이항 함수로 변환하는 데 사용되는 도우미 템플릿 함수입니다.|  
|[ref](../Topic/%3Cfunctional%3E%20functions.md#ref_function)|인수에서 `reference_wrapper`를 생성합니다.|  
|[스왑](../Topic/%3Cfunctional%3E%20functions.md#swap_function)|두 `function` 개체를 교환합니다.|  
  
### <a name="structs"></a>구조체  
  
|||  
|-|-|  
|[binary_function](../standard-library/binary-function-struct.md)|이항 함수 개체를 제공하는 파생 클래스에 상속될 수 있는 형식을 정의하는 빈 기본 클래스입니다.|  
|[분](../standard-library/divides-struct.md)|클래스는 지정된 값 형식의 요소에 대해 나누기 산술 연산을 수행하는 미리 정의된 함수 개체를 제공합니다.|  
|[equal_to](../standard-library/equal-to-struct.md)|지정된 형식의 값이 해당 형식의 다른 값과 같은지 테스트하는 이항 조건자입니다.|  
|[큰](../standard-library/greater-struct.md)|지정된 형식의 값이 해당 형식의 다른 값보다 큰지 테스트하는 이항 조건자입니다.|  
|[greater_equal](../standard-library/greater-equal-struct.md)|지정된 형식의 값이 해당 형식의 다른 값보다 크거나 같은지 테스트하는 이항 조건자입니다.|  
|[작음](../standard-library/less-struct.md)|지정된 형식의 값이 해당 형식의 다른 값보다 작은지 테스트하는 이항 조건자입니다.|  
|[less_equal](../standard-library/less-equal-struct.md)|지정된 형식의 값이 해당 형식의 다른 값보다 작거나 같은지 테스트하는 이항 조건자입니다.|  
|[logical_and](../standard-library/logical-and-struct.md)|이 클래스는 지정된 값 형식의 요소에 대해 논리곱 논리 연산을 수행하고 결과가 참 또는 거짓인지 테스트하는 미리 정의된 함수 개체를 제공합니다.|  
|[logical_not](../standard-library/logical-not-struct.md)|이 클래스는 지정된 값 형식의 요소에 대해 부정 논리 연산을 수행하고 결과가 참 또는 거짓인지 테스트하는 미리 정의된 함수 개체를 제공합니다.|  
|[logical_or](../standard-library/logical-or-struct.md)|이 클래스는 지정된 값 형식의 요소에 대해 분리 논리 연산을 수행하고 결과가 참 또는 거짓인지 테스트하는 미리 정의된 함수 개체를 제공합니다.|  
|[빼기](../standard-library/minus-struct.md)|이 클래스는 지정된 값 형식의 요소에 대해 빼기 산술 연산을 수행하는 미리 정의된 함수 개체를 제공합니다.|  
|[모듈러스](../standard-library/modulus-struct.md)|이 클래스는 지정된 값 형식의 요소에 대해 모듈러스 산술 연산을 수행하는 미리 정의된 함수 개체를 제공합니다.|  
|[multiplies](../standard-library/multiplies-struct.md)|이 클래스는 지정된 값 형식의 요소에 대해 곱하기 산술 연산을 수행하는 미리 정의된 함수 개체를 제공합니다.|  
|[부정합니다](../standard-library/negate-struct.md)|이 클래스는 요소 값의 부정을 반환하는 미리 정의된 함수 개체를 제공합니다.|  
|[not_equal_to](../standard-library/not-equal-to-struct.md)|지정된 형식의 값이 해당 형식의 다른 값과 같지 않은지 테스트하는 이항 조건자입니다.|  
|[더하기](../standard-library/plus-struct.md)|클래스는 지정된 값 형식의 요소에 대해 더하기 산술 연산을 수행하는 미리 정의된 함수 개체를 제공합니다.|  
|[unary_function](../standard-library/unary-function-struct.md)|단항 함수 개체를 제공하는 파생 클래스에 상속될 수 있는 형식을 정의하는 빈 기본 클래스입니다.|  
  
### <a name="objects"></a>체크 인  
  
|||  
|-|-|  
|[_1.._M](../standard-library/1-object.md)|대체 가능한 인수에 대한 자리 표시자입니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 = =](../Topic/%3Cfunctional%3E%20operators.md#operator_eq_eq)|호출 가능 개체의 같음 비교를 허용하지 않습니다.|  
|[연산자! =](../Topic/%3Cfunctional%3E%20operators.md#operator_neq)|호출 가능 개체의 같지 않음 비교를 허용하지 않습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

