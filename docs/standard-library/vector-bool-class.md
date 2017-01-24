---
title: "vector&lt;bool&gt; 클래스 | Microsoft Docs"
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
  - "vector<bool>"
  - "std.vector<bool>"
  - "std::vector<bool>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "벡터 < b o > 클래스"
ms.assetid: 8028c8ed-ac9c-4f06-aba1-5de45c00aafb
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vector&lt;bool&gt; 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

 `vector<bool>` 클래스의 부분 특수화는 [벡터](../standard-library/vector-class.md) 형식의 요소에 대 한 `bool`합니다. 특수화(비트당 하나의 `bool` 값을 저장하여 공간 최적화 제공)에서 사용하는 기본 형식에 대한 할당자가 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Allocator = allocator<bool>>  
class vector<bool, Allocator>  
```  
  
## <a name="remarks"></a>설명  
 이 클래스 템플릿 특수화는이 문서에서 설명 하는 차이 제외 하 고 벡터 처럼 동작 합니다.  
  
 `bool` 형식으로 처리되는 작업은 컨테이너 저장소의 값에 해당합니다. `allocator_traits::construct`는 이러한 값을 만드는 데 사용되지 않습니다.  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[const_pointer](#vector_lt_bool_gt___const_pointer)|`const_iterator`의 부울 요소에 대한 상수 포인터로 사용할 수 있는 `vector<bool>`에 대한 typedef입니다.|  
|[const_reference](#vector_lt_bool_gt___const_reference)|`bool`에 대한 typedef입니다. 초기화 이후에는 원래 값으로의 업데이트를 따르지 않습니다.|  
|[포인터](#vector_lt_bool_gt___pointer)|`iterator`의 부울 요소에 대한 포인터로 사용할 수 있는 `vector<bool>`에 대한 typedef입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[대칭 이동](#vector_lt_bool_gt___flip)|`vector<bool>`의 모든 비트를 반대로 바꿉니다.|  
|[스왑](#vector_lt_bool_gt___swap)|두 `vector<bool>`의 요소를 교환합니다.|  
|[연산자 &#91; &#93;](#vector_lt_bool_gt___operator_at)|지정된 위치에서 `vector<bool>` 요소에 대한 시뮬레이션 참조를 반환합니다.|  
|`at`|지정 되지 않은 동일 하 게 작동 [벡터](../standard-library/vector-class.md):: 함수를 사용 하 여 프록시 클래스 점을 제외 하 고 [벡터 \< bool>:: 참조](#vector_lt_bool_gt___reference_class)합니다. 또한 참조 [연산자 &#91; &#93;](#vector_lt_bool_gt___operator_at)합니다.|  
|`front`|지정 되지 않은 동일 하 게 작동 [벡터](../standard-library/vector-class.md):: 프록시 클래스를 사용 하 여 함수를 전면 [벡터 \< bool>:: 참조](#vector_lt_bool_gt___reference_class)합니다. 또한 참조 [연산자 &#91; &#93;](#vector_lt_bool_gt___operator_at)합니다.|  
|`back`|지정 되지 않은 동일 하 게 작동 [벡터](../standard-library/vector-class.md):: 프록시 클래스를 사용 하 여 함수를 다시 [벡터 \< bool>:: 참조](#vector_lt_bool_gt___reference_class)합니다. 또한 참조 [연산자 &#91; &#93;](#vector_lt_bool_gt___operator_at)합니다.|  
  
### <a name="proxy-class"></a>프록시 클래스  
  
|||  
|-|-|  
|[벡터 \< bool> 클래스 참조](#vector_lt_bool_gt___reference_class)|`bool&` 동작을 시뮬레이션하기 위해 프록시 역할을 하며, 해당 개체가 `vector<bool>` 개체 내 요소(단일 비트)에 대한 참조를 제공할 수 있는 클래스입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: \< 벡터>  
  
 **네임스페이스:** std  
  
##  <a name="a-namevectorltboolgtconstpointera-vectorboolconstpointer"></a><a name="vector_lt_bool_gt___const_pointer"></a>  벡터 \< bool>:: const_pointer  
 `vector<bool>` 개체에 포함된 시퀀스의 부울 요소에 대해 고정 포인터로 사용할 수 있는 개체를 설명하는 형식입니다.  
  
```  
typedef const_iterator const_pointer;  
```  
  
##  <a name="a-namevectorltboolgtconstreferencea-vectorboolconstreference"></a><a name="vector_lt_bool_gt___const_reference"></a>  벡터 \< bool>:: const_reference  
 `vector<bool>` 개체에 포함된 시퀀스의 부울 요소에 대해 고정 참조로 사용할 수 있는 개체를 설명하는 형식입니다.  
  
```  
typedef bool const_reference;  
```  
  
### <a name="remarks"></a>설명  
 자세한 내용과 코드 예제에 대 한 참조 [벡터&lt;bool&gt;:: reference::operator =](#vector_lt_bool_gt___reference_operator_eq)합니다.  
  
##  <a name="a-namevectorltboolgtflipa-vectorboolflip"></a><a name="vector_lt_bool_gt___flip"></a>  벡터 \< bool>:: 대칭 이동  
 `vector<bool>`의 모든 비트를 반대로 바꿉니다.  
  
```  
void flip();
```  
  
### <a name="example"></a>예제  
  
```cpp  
// vector_bool_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha; // format output for subsequent code  
  
    vector<bool> vb = { true, false, false, true, true };  
    cout << "The vector is:" << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vb.flip();  
  
    cout << "The flipped vector is:" << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
  
```  
  
##  <a name="a-namevectorltboolgtoperatorata-vectorbooloperator"></a><a name="vector_lt_bool_gt___operator_at"></a>  벡터 \< bool>:: operator  
 지정된 위치에서 `vector<bool>` 요소에 대한 시뮬레이션 참조를 반환합니다.  
  
```  
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|`Pos`|`vector<bool>` 요소의 위치입니다.|  
  
### <a name="return-value"></a>반환 값  
 A [벡터 \< bool>:: 참조](#vector_lt_bool_gt___reference_class) 또는 [벡터 \< bool>:: const_reference](#vector_lt_bool_gt___const_reference) 인덱싱된 요소의 값을 포함 하는 개체입니다.  
  
 지정된 위치가 컨테이너의 크기보다 크거나 같을 경우 결과가 정의되지 않습니다.  
  
### <a name="remarks"></a>설명  
 `_ITERATOR_DEBUG_LEVEL` 집합을 사용하여 컴파일할 경우 벡터 경계 밖에서 요소를 액세스하려고 하면 런타임 오류가 발생합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md)을 참조하세요.  
  
### <a name="example"></a>예제  
  이 코드 예제는 `vector<bool>::operator[]`의 올바른 사용 방법과 두 가지 흔한 코딩 실수(주석 처리)를 보여 줍니다. 이러한 실수는 `vector<bool>::reference`에서 반환하는 `vector<bool>::operator[]` 개체의 주소를 가져올 수 없으므로 오류가 발생합니다.  
  
```cpp  
  
// cl.exe /EHsc /nologo /W4 /MTd   
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
    vector<bool> vb;  
  
    vb.push_back(true);  
    vb.push_back(false);  
  
    //    bool* pb = &vb[1]; // conversion error -                         do not use  
    //    bool& refb = vb[1];   // conversion error -                         do not use  
    bool hold = vb[1];  
    cout << "The second element of vb is " << vb[1] << endl;  
    cout << "The held value from the second element of vb is " << hold << endl;  
  
    // Note this doesn't modify hold.  
    vb[1] = true;  
    cout << "The second element of vb is " << vb[1] << endl;  
    cout << "The held value from the second element of vb is " << hold << endl;  
}  
  
```  
  
##  <a name="a-namevectorltboolgtpointera-vectorboolpointer"></a><a name="vector_lt_bool_gt___pointer"></a>  벡터 \< bool>:: 포인터  
 `vector<bool>` 개체에 포함된 시퀀스의 부울 요소에 대해 포인터로 사용할 수 있는 개체를 설명하는 형식입니다.  
  
```  
typedef iterator pointer;  
```  
  
##  <a name="a-namevectorltboolgtreferenceclassa-vectorboolreference-class"></a><a name="vector_lt_bool_gt___reference_class"></a>  벡터 \< bool>:: reference 클래스  
  `vector<bool>::reference` 에서 제공 하는 프록시 클래스는 [벡터 \< bool> 클래스](../standard-library/vector-bool-class.md) 시뮬레이션할 `bool&`합니다.  
  
### <a name="remarks"></a>설명  
 C++는 기본적으로 비트에 직접 참조를 허용하지 않으므로 시뮬레이션된 참조가 필요하지 않습니다. `vector<bool>`는 요소당 1비트만 사용하며, 이 프록시 클래스만 사용하여 참조할 수 있습니다. 하지만, 특정 할당은 유효하지 않으므로 참조 시뮬레이션이 완전하지 않습니다. 예를 들어 때문에의 주소는 `vector<bool>::reference` 개체 가져올 수 없으므로, 다음 코드를 사용 하 여 [벡터 \< bool>:: 연산자 &#91; &#93;](#vector_lt_bool_gt___operator_at) 올바르지 않습니다.  
  
```cpp  
    vector<bool> vb;  
...  
    bool* pb = &vb[1]; // conversion error -         do not use  
    bool& refb = vb[1];   // conversion error -         do not use  
```  
  
###  <a name="a-namevectorltboolgtreferenceflipa-vectorboolreferenceflip"></a><a name="vector_lt_bool_gt___reference_flip"></a>  벡터 \< bool>:: reference:: flip  
 참조 된 부울 값을 반전 [벡터 \< bool>](../standard-library/vector-bool-class.md) 요소입니다.  
  
```  
void flip();
```  
  
#### <a name="remarks"></a>설명  
  
#### <a name="example"></a>예제  
  
```cpp  
// vector_bool_ref_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    cout << "The vector is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vector<bool>::reference vbref = vb.front();  
    vbref.flip();  
  
    cout << "The vector with first element flipped is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
/* Output:  
The vector is:  
    true false false true true  
The vector with first element flipped is:  
    false false false true true  
    */  
  
```  
  
###  <a name="a-namevectorltboolgtreferenceoperatorboola-vectorboolreferenceoperator-bool"></a><a name="vector_lt_bool_gt___reference_operator_bool"></a>  벡터 \< bool>:: operator bool  
 `vector<bool>::reference`을 `bool`로 묵시적으로 변환합니다.  
  
' ' 연산자 bool() const;
```  
  
#### Return Value  
 The Boolean value of the element of the vector<bool\> object.  
  
#### Remarks  
 The `vector<bool>` object cannot be modified by this operator.  
  
###  <a name="vector_lt_bool_gt___reference_operator_eq"></a>  vector<bool\>::reference::operator=  
 Assigns a Boolean value to a bit, or the value held by a referenced element to a bit.  
  
```  
참조 & 연산자 (const 참조 및 오른쪽) =;

참조 & 연산자 =(bool Val);
```  
  
#### Parameters  
 `Right`  
 The element reference whose value is to be assigned to the bit.  
  
 `Val`  
 The Boolean value to be assigned to the bit.  
  
#### Example  
  
```cpp  
// vector_bool_ref_op_assign.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    print("The vector is: ", vb);  
  
    // Invoke vector<bool>::reference::operator=()  
    vector<bool>::reference refelem1 = vb[0];  
    vector<bool>::reference refelem2 = vb[1];  
    vector<bool>::reference refelem3 = vb[2];  
  
    bool b1 = refelem1;  
    bool b2 = refelem2;  
    bool b3 = refelem3;  
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;  
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;  
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;  
    cout << endl;  
  
    refelem2 = refelem1;  
  
    print("The vector after assigning refelem1 to refelem2 is now: ", vb);  
  
    refelem3 = true;  
  
    print("The vector after assigning false to refelem1 is now: ", vb);  
  
    // The initial values are still stored in the bool variables and remained unchanged  
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;  
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;  
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;  
    cout << endl;  
}  
/* Output:  
The vector is: true false false true true  
The original value of the 1st element stored in a bool: true  
The original value of the 2nd element stored in a bool: false  
The original value of the 3rd element stored in a bool: false  
  
The vector after assigning refelem1 to refelem2 is now: true true false true true  
The vector after assigning false to refelem1 is now: true true true true true  
The original value of the 1st element still stored in a bool: true  
The original value of the 2nd element still stored in a bool: false  
The original value of the 3rd element still stored in a bool: false  
*/  
  
```  
  
##  <a name="a-namevectorltboolgtswapa-vectorboolswap"></a><a name="vector_lt_bool_gt___swap"></a>  벡터 \< bool>:: swap  
 부울 벡터의 두 요소를 교환 하는 정적 멤버 함수 ( `vector<bool>`) 프록시 클래스를 사용 하 여 [벡터 \< bool>:: 참조](#vector_lt_bool_gt___reference_class)합니다.  
  
```  
 
static void swap(
    reference Left,  
    reference Right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Left`  
 `Right` 요소와 교환할 요소입니다.  
  
 `Right`  
 `Left` 요소와 교환할 요소입니다.  
  
### <a name="remarks"></a>설명  
 이 오버로드는 `vector<bool>`의 특정 프록시 요구 사항을 지원합니다. [벡터](../standard-library/vector-class.md):: swap는 단일 인수 오버 로드와 같은 기능 `vector<bool>::swap()`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)

