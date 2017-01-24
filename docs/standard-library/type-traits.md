---
title: "&lt;type_traits&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<type_traits>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typetrait 헤더[TR1]"
  - "type_traits"
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
caps.latest.revision: 35
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;type_traits&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 인수의 속성에 대 한 정보를 제공 하거나 생성 하는 컴파일 타임 상수 형식 변환 제공 하는 템플릿을 정의 합니다.  
  
## 구문  
  
```  
#include <type_traits>  
```  
  
## 설명  
 클래스 및 템플릿을 `<type_traits>` 형식 유추, 분류 및 형식 관련 오류를 감지 하 고 일반 코드를 최적화할 수 있도록 컴파일 타임에 변환을 지 원하는 데 사용 됩니다. 이러한 클래스와 템플릿 단항 형식 특성을 형식의 속성을 설명 하는 형식 및 형식 속성을 수정 하는 변환 특성 간의 관계를 설명 하는 이진 형식 특성을 포함 합니다.  
  
 형식 특성, 도우미 클래스를 지원 하기 위해 `integral_constant`, 정의 됩니다. 템플릿 특수화가 `true_type` 및 `false_type` 형식 조건자에 대 한 기본 클래스를 형성 하는 합니다. A *형식 조건자* 는 하나 이상의 형식 인수를 사용 하는 템플릿입니다. 형식 조건자가 *true*인 경우 [true\_type](../Topic/true_type%20Typedef.md)에서 직접 또는 간접적으로 공개 파생됩니다. 형식 조건자가 *false*인 경우 [false\_type](../Topic/false_type%20Typedef.md)에서 직접 또는 간접적으로 공개 파생됩니다.  
  
 A *유형 한정자* 또는 *변환 성분* 는 하나 이상의 템플릿 인수를 사용 하는 서식 파일 및 멤버를 하나가지고 `type`, 수정 된 형식에 대 한 동의어입니다.  
  
### 별칭 템플릿  
 형식 특성 식을 단순화 하 [별칭 템플릿](../cpp/aliases-and-typedefs-cpp.md) 에 대 한 `typename some_trait<T>::type` 는 제공 됩니다. 여기서 " `some_trait`"는 템플릿 클래스 이름입니다. 예를 들어 [add\_const](../standard-library/add-const-class.md) 에 해당 형식에 대 한 별칭 템플릿 `add_const_t`, 로 정의 합니다.  
  
```cpp  
template<class T>  
    using add_const_t = typename add_const<T>::type;  
```  
  
|||||  
|-|-|-|-|  
|add\_const\_t|aligned\_storage\_t|make\_signed\_t|remove\_pointer\_t|  
|add\_cv\_t|aligned\_union\_t|make\_unsigned\_t|remove\_reference\_t|  
|add\_lvalue\_reference\_t|common\_type\_t|remove\_all\_extents\_t|remove\_volatile\_t|  
|add\_pointer\_t|conditional\_t|remove\_const\_t|result\_of\_t|  
|add\_rvalue\_reference\_t|decay\_t|remove\_cv\_t|underlying\_type\_t|  
|add\_volatile\_t|enable\_if\_t|remove\_extent\_t||  
  
### 클래스  
 도우미 클래스 및 typedef  
  
|||  
|-|-|  
|[integral\_constant](../standard-library/integral-constant-class-bool-constant-class.md)|형식 및 값에서 정수 계열을 상수를 만듭니다.|  
|[true\_type](../Topic/true_type%20Typedef.md)|값이 true인 정수 상수를 보관합니다.|  
|[false\_type](../Topic/false_type%20Typedef.md)|값이 false인 정수 상수를 보관합니다.|  
  
 기본 형식 범주  
  
|||  
|-|-|  
|[is\_void](../standard-library/is-void-class.md)|형식 인지를 테스트 `void`합니다.|  
|[is\_null\_pointer](../standard-library/is-null-pointer-class.md)|형식 인지를 테스트 `std::nullptr_t`합니다.|  
|[is\_integral](../standard-library/is-integral-class.md)|형식이 정수인지 테스트합니다.|  
|[is\_floating\_point](../standard-library/is-floating-point-class.md)|형식이 부동 소수점인지 테스트합니다.|  
|[is\_array](../standard-library/is-array-class.md)|형식이 배열형인지 테스트합니다.|  
|[is\_pointer](../standard-library/is-pointer-class.md)|형식이 포인터인지 테스트합니다.|  
|[is\_lvalue\_reference](../standard-library/is-lvalue-reference-class.md)|형식이 lvalue 참조인지 여부를 테스트합니다.|  
|[is\_rvalue\_reference](../standard-library/is-rvalue-reference-class.md)|형식이 rvalue 참조인지 테스트합니다.|  
|[is\_member\_object\_pointer](../standard-library/is-member-object-pointer-class.md)|형식이 멤버 개체에 대한 포인터인지 테스트합니다.|  
|[is\_member\_function\_pointer](../standard-library/is-member-function-pointer-class.md)|형식이 멤버 함수에 대한 포인터인지 테스트합니다.|  
|[is\_enum](../standard-library/is-enum-class.md)|형식이 열거형인지 테스트합니다.|  
|[is\_union](../standard-library/is-union-class.md)|형식이 공용 구조체인지 테스트합니다.|  
|[is\_class](../standard-library/is-class-class.md)|형식이 클래스인지 테스트합니다.|  
|[is\_function](../standard-library/is-function-class.md)|형식이 함수 형식인지 테스트합니다.|  
  
 복합 형식 범주  
  
|||  
|-|-|  
|[is\_reference](../standard-library/is-reference-class.md)|형식이 참조인지 테스트합니다.|  
|[is\_arithmetic](../standard-library/is-arithmetic-class.md)|형식이 산술형인지 테스트합니다.|  
|[is\_fundamental](../standard-library/is-fundamental-class.md)|형식이 `void` 또는 산술형인지 테스트합니다.|  
|[is\_object](../standard-library/is-object-class.md)|형식이 개체 형식인지 테스트합니다.|  
|[is\_scalar](../standard-library/is-scalar-class.md)|형식이 스칼라 형식인지 테스트합니다.|  
|[is\_compound](../standard-library/is-compound-class.md)|형식이 스칼라가 아닌지 테스트합니다.|  
|[is\_member\_pointer](../standard-library/is-member-pointer-class.md)|형식이 멤버에 대한 포인터인지 테스트합니다.|  
  
 형식 속성  
  
|||  
|-|-|  
|[is\_const](../standard-library/is-const-class.md)|형식 인지를 테스트 `const`합니다.|  
|[is\_volatile](../standard-library/is-volatile-class.md)|형식 인지를 테스트 `volatile`합니다.|  
|[is\_trivial](../standard-library/is-trivial-class.md)|형식이 trivial 인지 테스트 합니다.|  
|[is\_trivially\_copyable](../standard-library/is-trivially-copyable-class.md)|형식은 일반적으로 복사할 수 있는지 테스트 합니다.|  
|[is\_standard\_layout](../standard-library/is-standard-layout-class.md)|형식이 표준 레이아웃 인지 테스트를 입력 합니다.|  
|[is\_pod](../standard-library/is-pod-class.md)|형식이 POD인지 테스트합니다.|  
|[is\_literal\_type](../standard-library/is-literal-type-class.md)|형식을 사용할 수 있는지 여부를 테스트 한 `constexpr` 변수나에 사용 되는 한 `constexpr` 함수입니다.|  
|[is\_empty](../standard-library/is-empty-class.md)|형식이 빈 클래스인지 테스트합니다.|  
|[is\_polymorphic](../standard-library/is-polymorphic-class.md)|형식이 다형 클래스 인지 테스트 합니다.|  
|[is\_abstract](../standard-library/is-abstract-class.md)|형식이 추상 클래스인지 테스트합니다.|  
|[is\_final](../standard-library/is-final-class.md)|형식이 클래스 형식이 표시 되어 있는지 여부를 테스트 `final`합니다.|  
|[is\_signed](../standard-library/is-signed-class.md)|형식이 부호 있는 정수인지 테스트합니다.|  
|[is\_unsigned](../standard-library/is-unsigned-class.md)|형식이 부호가 없는 정수인지 테스트합니다.|  
|[is\_constructible](../standard-library/is-constructible-class.md)|형식이 지정 된 인수 형식을 사용 하 여 만들게 되며 인지 테스트 합니다.|  
|[is\_default\_constructible](../standard-library/is-default-constructible-class.md)|형식에 기본 생성자가 있는지 테스트 합니다.|  
|[is\_copy\_constructible](../standard-library/is-copy-constructible-class.md)|형식에는 복사 생성자가 있는지 테스트 합니다.|  
|[is\_move\_constructible](../standard-library/is-move-constructible-class.md)|형식에 이동 생성자 있는지 테스트 합니다.|  
|[is\_assignable](../standard-library/is-assignable-class.md)|첫 번째 형식을 두 번째 형식의 값을 할당할 수 있는지 테스트 합니다.|  
|[is\_copy\_assignable](../standard-library/is-copy-assignable-class.md)|형식을 형식의 const 참조 값을 할당할 수 있는지 테스트 합니다.|  
|[is\_move\_assignable](../standard-library/is-move-assignable-class.md)|형식이 형식의 rvalue 참조를 할당 될 수 있는지 테스트 합니다.|  
|[is\_destructible](../standard-library/is-destructible-class.md)|형식이 소멸 가능한지 테스트합니다.|  
|[is\_trivially\_constructible](../standard-library/is-trivially-constructible-class.md)|지정된 된 형식을 사용 하 여 생성할 때 없는 특수 작업을 사용 하는 형식 인지 테스트 합니다.|  
|[is\_trivially\_default\_constructible](../standard-library/is-trivially-default-constructible-class.md)|형식을 생성 하는 기본 특수 작업을 사용 하는지 여부를 테스트 합니다.|  
|[is\_trivially\_copy\_constructible](../standard-library/is-trivially-copy-constructible-class.md)|형식 복사본 생성 될 때 특수 작업을 사용 하는지 여부를 테스트 합니다.|  
|[is\_trivially\_move\_constructible](../standard-library/is-trivially-move-constructible-class.md)|형식 이동 생성 될 때 특수 작업을 사용 하는지 여부를 테스트 합니다.|  
|[is\_trivially\_assignable](../standard-library/is-trivially-assignable-class.md)|유형은 할당할 수 없는 특수 작업을 사용 하 여 할당 있는지 여부를 테스트 합니다.|  
|[is\_trivially\_copy\_assignable](../standard-library/is-trivially-copy-assignable-class.md)|특수 작업을 사용 하 여 할당할 수 있는 복사 및 할당 인지 테스트 합니다.|  
|[is\_trivially\_move\_assignable](../standard-library/is-trivially-move-assignable-class.md)|특수 작업을 사용 하 여 할당할 수 있는 위치와 할당 인지 테스트 합니다.|  
|[is\_trivially\_destructible](../standard-library/is-trivially-destructible-class.md)|형식이 파괴할 수 있는 특수 작업을 사용 하 여 소멸자가 있는지 여부를 테스트 합니다.|  
|[is\_nothrow\_constructible](../standard-library/is-nothrow-constructible-class.md)|형식을 생성 하 고 지정된 된 형식을 사용 하 여 생성할 때 throw 것으로 알려진 있는지 테스트 합니다.|  
|[is\_nothrow\_default\_constructible](../standard-library/is-nothrow-default-constructible-class.md)|테스트는 만들게 되며 기본 형식이 인지와 것으로 알려진 기본 생성 될 때 발생 합니다.|  
|[is\_nothrow\_copy\_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|형식이 만들게 되며 복사 하 고 복사 생성자를 사용 하는 것으로 알려진 throw 하는지 여부를 테스트 합니다.|  
|[is\_nothrow\_move\_constructible](../standard-library/is-nothrow-move-constructible-class.md)|형식이 생성 가능 이동 하 고 이동 생성자를 throw 알려져 있는지 테스트 합니다.|  
|[is\_nothrow\_assignable](../standard-library/is-nothrow-assignable-class.md)|형식이 지정된 된 형식을 사용 하 여 할당 및 할당 것으로 알려진 throw 있는지 테스트 합니다.|  
|[is\_nothrow\_copy\_assignable](../standard-library/is-nothrow-copy-assignable-class.md)|복사를 할당할 수 있는 형식이 할당 것으로 알려진 throw 있는지 여부를 테스트 합니다.|  
|[is\_nothrow\_move\_assignable](../standard-library/is-nothrow-move-assignable-class.md)|이동 할당 가능한 형식이 할당 것으로 알려진 throw 있는지 여부를 테스트 합니다.|  
|[is\_nothrow\_destructible](../standard-library/is-nothrow-destructible-class.md)|형식이 적인 소멸자를 throw 알려져 있는지 여부를 테스트 합니다.|  
|[has\_virtual\_destructor](http://msdn.microsoft.com/ko-kr/c0f85f0b-c63c-410d-a046-72eeaf44f7eb)|형식에 가상 소멸자가 있는지 테스트합니다.|  
  
 형식 속성 쿼리  
  
|||  
|-|-|  
|[alignment\_of](../standard-library/alignment-of-class.md)|형식의 맞춤을 가져옵니다.|  
|[rank](../standard-library/rank-class.md)|배열 차원 수를 가져옵니다.|  
|[extent](../standard-library/extent-class.md)|지정 된 배열 차원에서 요소의 수를 가져옵니다.|  
  
 형식 관계  
  
|||  
|-|-|  
|[is\_same](../standard-library/is-same-class.md)|두 형식이 동일한지 테스트합니다.|  
|[is\_base\_of](../standard-library/is-base-of-class.md)|한 형식 다른 형식의 기본 형식 인지 테스트 합니다.|  
|[is\_convertible](../standard-library/is-convertible-class.md)|한 가지 형식을 다른 형식으로 변환할 수 있는지 테스트합니다.|  
  
 Volatile const 수정  
  
|||  
|-|-|  
|[add\_const](../standard-library/add-const-class.md)|생성 된 `const` 형식에서 형식이 있습니다.|  
|[add\_volatile](../standard-library/add-volatile-class.md)|생성 된 `volatile` 형식에서 형식이 있습니다.|  
|[add\_cv](../standard-library/add-cv-class.md)|생성 된 `const``volatile` 형식에서 형식이 있습니다.|  
|[remove\_const](../standard-library/remove-const-class.md)|형식에서 비 const 형식을 만듭니다.|  
|[remove\_volatile](../standard-library/remove-volatile-class.md)|형식에서 비휘발성 형식을 만듭니다.|  
|[remove\_cv](../standard-library/remove-cv-class.md)|형식에서 const가 아닌 비휘발성 형식을 만듭니다.|  
  
 참조 수정  
  
|||  
|-|-|  
|[add\_lvalue\_reference](../standard-library/add-lvalue-reference-class.md)|형식에서 형식에 대 한 참조를 생성 합니다.|  
|[add\_rvalue\_reference](../standard-library/add-rvalue-reference-class.md)|형식에서 형식에 대 한 rvalue 참조를 생성 합니다.|  
|[remove\_reference](../standard-library/remove-reference-class.md)|형식에서 비참조 형식을 만듭니다.|  
  
 부호 수정  
  
|||  
|-|-|  
|[make\_signed](../standard-library/make-signed-class.md)|서명 하는 경우 형식 또는 가장 작은 부호 있는 형식 보다 크거나 같은 크기의 형식으로 생성 합니다.|  
|[make\_unsigned](../standard-library/make-unsigned-class.md)|생성, 서명 되지 않은 경우 형식 또는 가장 작은 부호 없는 형식 보다 크거나 같은 크기에서를 입력 합니다.|  
  
 배열 수정  
  
|||  
|-|-|  
|[remove\_all\_extents](../standard-library/remove-all-extents-class.md)|배열 형식에서 배열이 아닌 형식을 생성합니다.|  
|[remove\_extent](../standard-library/remove-extent-class.md)|배열 형식에서 요소 형식을 생성합니다.|  
  
 포인터 수정  
  
|||  
|-|-|  
|[add\_pointer](../standard-library/add-pointer-class.md)|형식에서 형식에 대 한 포인터를 생성 합니다.|  
|[remove\_pointer](../standard-library/remove-pointer-class.md)|입력에 대 한 포인터에서 형식을 생성 합니다.|  
  
 기타 변환  
  
|||  
|-|-|  
|[aligned\_storage](../standard-library/aligned-storage-class.md)|정렬된 형식에 대해 초기화되지 않은 메모리를 할당합니다.|  
|[aligned\_union](../standard-library/aligned-union-class.md)|특수한 생성자 또는 소멸자를 사용하여 정렬된 공용 구조체에 대해 초기화되지 않은 메모리를 할당합니다.|  
|[common\_type](../standard-library/common-type-class.md)|모든 유형의 매개 변수 팩의 공용 형식을 생성합니다.|  
|[conditional](../standard-library/conditional-class.md)|조건이 true 이면 첫 번째 지정된 된 형식, 그렇지 않으면 지정된 된 두 번째 형식을 생성 합니다.|  
|[decay](../standard-library/decay-class.md)|값으로 전달 될 때 형식을 생성 합니다. 비참조, 비상수, 비휘발성 형식 또는 형식에 대한 포인터를 만듭니다.|  
|[enable\_if](../standard-library/enable-if-class.md)|조건이 true 이면 지정된 된 형식, 그렇지 않으면 형식이 없는 생성 합니다.|  
|[result\_of](../standard-library/result-of-class1.md)|지정 된 인수 형식을 사용 하는 호출 가능한 형식의 반환 형식을 결정 합니다.|  
|[underlying\_type](../standard-library/underlying-type-class.md)|열거형 형식에 대 한 내부 정수 계열 형식을 생성합니다.|  
  
## 참고 항목  
 [\<functional\>](../standard-library/functional.md)