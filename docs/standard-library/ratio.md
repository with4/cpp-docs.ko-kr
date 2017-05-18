---
title: '&lt;ratio&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ratio/std::mega
- ratio/std::peta
- ratio/std::ratio_greater
- ratio/std::micro
- ratio/std::ratio_add
- ratio/std::ratio_not_equal
- ratio/std::hecto
- ratio/std::nano
- ratio/std::ratio_less_equal
- ratio/std::ratio_less
- ratio/std::centi
- ratio/std::ratio_greater_equal
- ratio/std::ratio_subtract
- <ratio>
- ratio/std::atto
- ratio/std::tera
- ratio/std::milli
- ratio/std::ratio_multiply
- ratio/std::kilo
- ratio/std::ratio_divide
- ratio/std::giga
- ratio/std::pico
- ratio/std::femto
- ratio/std::ratio_equal
- ratio/std::ratio
- ratio/std::exa
- ratio/std::deci
- ratio/std::deca
dev_langs:
- C++
ms.assetid: 8543e912-2d84-45ea-b3c0-bd7bfacee405
caps.latest.revision: 14
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 39fdef1976a506c36a553d575c83462e7c6e9ee0
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ltratiogt"></a>&lt;ratio&gt;
표준 헤더 \<ratio>를 포함하여 컴파일 시간에 유리수를 저장하고 조작하는 데 사용되는 상수와 템플릿을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
#include <ratio>  
```  
  
### <a name="ratio-structure"></a>ratio 구조체  

```
struct ratio
{
    static constexpr intmax_t num;
    static constexpr intmax_t den;
    typedef ratio<num, den>  type;
};
```  
 [ratio 구조체](http://msdn.microsoft.com/en-us/3f7961f4-802b-4251-b3c3-090ef91c0dba)는 `num` / `den` == N / D이고 `num` 및 `den`에는 공약수가 없도록 정적 상수 `num` 및 `den`을 정의합니다. `num` / `den`은 템플릿 클래스로 표시되는 `value`입니다. 따라서 `type`은 `num` == N0이고 `den` == D0인 인스턴스화 `ratio<N0, D0>`을 지정합니다.  
  
### <a name="specializations"></a>특수화  
 \<ratio>는 다음 형식으로 된 `ratio` 특수화도 정의합니다.  
  
 `template <class R1, class R2> struct ratio_specialization`  
  
 각 특수화에서는 템플릿 매개 변수 두 개를 사용하는데, 이 두 매개 변수 역시 `ratio`의 특수화여야 합니다. `type`의 값은 관련 논리 연산을 통해 결정됩니다.  
  
|이름|`type` 값|  
|----------|------------------|  
|`ratio_add`|`R1 + R2`|  
|`ratio_divide`|`R1 / R2`|  
|`ratio_equal`|`R1 == R2`|  
|`ratio_greater`|`R1 > R2`|  
|`ratio_greater_equal`|`R1 >= R2`|  
|`ratio_less`|`R1 < R2`|  
|`ratio_less_equal`|`R1 <= R2`|  
|`ratio_multiply`|`R1 * R2`|  
|`ratio_not_equal`|`!(R1 == R2)`|  
|`ratio_subtract`|`R1 - R2`|  
  
### <a name="typedefs"></a>형식 정의  
  
```
typedef ratio<1,  1000000000000000000> atto;
typedef ratio<1,     1000000000000000> femto;
typedef ratio<1,        1000000000000> pico;
typedef ratio<1, 1000000000> nano;
typedef ratio<1, 1000000> micro;
typedef ratio<1, 1000> milli;
typedef ratio<1,  100> centi;
typedef ratio<1,   10> deci;
typedef ratio<10, 1> deca;
typedef ratio<100, 1> hecto;
typedef ratio<1000, 1> kilo;
typedef ratio<1000000, 1> mega;
typedef ratio<1000000000, 1> giga;
typedef ratio<1000000000000, 1> tera;
typedef ratio<1000000000000000, 1> peta;
typedef ratio<1000000000000000000, 1> exa;
```  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)




