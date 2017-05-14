---
title: "binder2nd 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- binder2nd
- xfunctional/std::binder2nd
dev_langs:
- C++
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
caps.latest.revision: 22
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 9a2f3f31798d1cdadf00e95b9f393e93a20d29ea
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="binder2nd-class"></a>binder2nd 클래스
이항 함수의 두 번째 인수를 지정된 값에 바인딩하여 이항 함수 개체를 단항 함수 개체로 변환하는 생성자를 제공하는 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& Func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;

protected:
    Operation op;
    typename Operation::second_argument_type value;
};
```  
  
#### <a name="parameters"></a>매개 변수  
 `Func`  
 단항 함수 개체로 변환할 이항 함수 개체입니다.  
  
 `right`  
 이항 함수 개체의 두 번째 인수가 바인딩되는 값입니다.  
  
 `left`  
 수정된 이진 개체를 두 번째 인수의 고정 값과 비교하는 인수의 값입니다.  
  
## <a name="return-value"></a>반환 값  
 이항 함수 개체의 두 번째 인수를 `right.` 값에 바인딩할 때 생성되는 단항 함수 개체입니다.  
  
## <a name="remarks"></a>설명  
 템플릿 클래스는 이항 함수 개체 _ *Func*의 복사본을 **op**에, `right`의 복사본을 **value**에 저장합니다. 그리고 **op**( `left`, **value**)를 반환하도록 해당 멤버 함수 `operator()`를 정의합니다.  
  
 `Func`가 **Operation** 형식의 개체이고 c가 상수이면 [bind2nd](../standard-library/functional-functions.md#bind2nd) ( `Func`, `c` )는 `binder2nd` 클래스 생성자 `binder2nd`\< **Operation**> ( `Func`, `c` )와 등가이고 더 편리합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// functional_binder2nd.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int>::iterator Iter;  
  
    int i;  
    for (i = 0; i <= 5; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    // Count the number of integers > 10 in the vector  
    vector<int>::iterator::difference_type result1;  
    result1 = count_if(v1.begin(), v1.end(),  
        binder2nd<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare using binder1st fixing 1st argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder1st<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 less than 10 is: "  
         << result2 << "." << endl;  
}  
/* Output:  
The vector v1 = ( 0 5 10 15 20 25 )  
The number of elements in v1 greater than 10 is: 3.  
The number of elements in v1 less than 10 is: 2.  
*/  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<functional>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)




