---
title: 왼쪽된 시프트 및 오른쪽 시프트 연산자 (&gt; &gt; 및 &lt; &lt;) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- <<
- '>>'
dev_langs:
- C++
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d8835d096575f3f7a9d50c7be26fa435e5d6bcd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>왼쪽된 시프트 및 오른쪽 시프트 연산자 (&gt; &gt; 및 &lt; &lt;)
비트 시프트 연산자는 오른쪽 시프트 연산자 (>>)의 비트 이동 *shift 식* 오른쪽 및 왼쪽 시프트 연산자 (<<)의 비트를 이동 하 *shift 키를 누른 채 식* 왼쪽에 있습니다. <sup>1</sup>  
  
## <a name="syntax"></a>구문  
  
> *shift 식* `<<` *덧셈 식*  
> *shift 식* `>>` *덧셈 식*  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
> 다음 설명 및 예제는 X86 및 x64 아키텍처용 Windows에 대해 유효합니다. 왼쪽 시프트 및 오른쪽 시프트 연산자를 구현하는 방법은 ARM 장치용 Windows RT에서는 상당히 다릅니다. 자세한 내용은의 "시프트 연산자" 섹션을 참조 하십시오.는 [Hello ARM](http://blogs.msdn.com/b/vcblog/archive/2012/10/25/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c.aspx) 블로그 게시물입니다.  
  
## <a name="left-shifts"></a>왼쪽 시프트  
 왼쪽 시프트 연산자의 bits *shift 식* 지정 된 위치 수 만큼 왼쪽으로 이동 *덧셈 식*합니다. 시프트 연산으로 비워진 비트 위치는 0으로 채워집니다. 왼쪽 시프트는 논리 시프트입니다(부호 비트를 포함해 끝에서 벗어나 이동한 비트는 무시됨). 비트 시프트 종류에 대 한 자세한 내용은 참조 [비트 시프트](http://en.wikipedia.org/wiki/Bitwise_shift)합니다.  
  
 다음 예제에서는 부호 없는 숫자를 사용하는 왼쪽 시프트 연산을 보여 줍니다. 예제에서는 값을 비트 집합으로 나타내어 비트에서 어떤 일이 발생하는지 보여 줍니다. 자세한 내용은 참조 [bitset 클래스](../standard-library/bitset-class.md)합니다.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short1 = 4;      
    bitset<16> bitset1{short1};   // the bitset representation of 4  
    cout << bitset1 << endl;  // 0000000000000100  
  
    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;  // 0000000000001000  
  
    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16  
    bitset<16> bitset3{short3};  
    cout << bitset3 << endl;  // 0000000000010000  
}  
  
```  
  
 부호 비트가 영향을 받도록 부호 있는 숫자를 왼쪽 시프트하면 결과가 정의되지 않습니다. 다음 예제에서는 1비트가 부호 비트 위치로 왼쪽 이동하면 Visual C++에서 어떤 일이 발생하는지 보여 줍니다.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 16384;      
    bitset<16> bitset1{short2};  
    cout << bitset1 << endl;  // 0100000000000000   
  
    short short3 = short1 << 1;  
    bitset<16> bitset3{short3};  // 16384 left-shifted by 1 = -32768  
    cout << bitset3 << endl;  // 100000000000000  
  
    short short4 = short1 << 14;  
    bitset<16> bitset4{short4};  // 4 left-shifted by 14 = 0  
    cout << bitset4 << endl;  // 000000000000000    
}  
```  
  
## <a name="right-shifts"></a>오른쪽 시프트  
 오른쪽 시프트 연산자를 통해 비트 패턴이에 *shift 식* 지정 된 위치 수 만큼 오른쪽으로 이동 *덧셈 식*합니다. 부호 없는 숫자의 경우 시프트 연산으로 비워진 비트 위치는 0으로 채워집니다. 부호 있는 숫자의 경우 부호 비트는 비워진 비트 위치를 채우는 데 사용됩니다. 즉, 숫자가 양수이면 0이 사용되고 숫자가 음수이면 1이 사용됩니다.  
  
> [!IMPORTANT]
> 부호 있는 음수의 오른쪽 시프트 결과는 구현에 따라 다릅니다. Visual C++는 부호를 사용하여 비워진 비트 위치를 채우지만 다른 구현도 마찬가지라는 보장은 없습니다.  
  
 이 예제에서는 부호 없는 숫자를 사용하는 오른쪽 시프트 연산을 보여 줍니다.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short11 = 1024;  
    bitset<16> bitset11{short11};  
    cout << bitset11 << endl;     // 0000010000000000  
  
    unsigned short short12 = short11 >> 1;  // 512  
    bitset<16> bitset12{short12};  
    cout << bitset12 << endl;     // 0000001000000000  
  
    unsigned short short13 = short11 >> 10;  // 1  
    bitset<16> bitset13{short13};  
    cout << bitset13 << endl;     // 0000000000000001  
  
    unsigned short short14 = short11 >> 11;  // 0  
    bitset<16> bitset14{short14};  
    cout << bitset14 << endl;     // 0000000000000000}  
}  
```  
  
 다음 예제에서는 부호 있는 양수를 사용하는 오른쪽 시프트 연산을 보여 줍니다.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 1024;  
    bitset<16> bitset1{short1};  
    cout << bitset1 << endl;     // 0000010000000000  
  
    short short2 = short1 >> 1;  // 512  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;     // 0000001000000000  
  
    short short3 = short1 >> 11;  // 0  
    bitset<16> bitset3{short3};     
    cout << bitset3 << endl;     // 0000000000000000  
}  
```  
  
 다음 예제에서는 부호 있는 음수를 사용하는 오른쪽 시프트 연산을 보여 줍니다.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short neg1 = -16;  
    bitset<16> bn1{neg1};  
    cout << bn1 << endl;  // 1111111111110000  
  
    short neg2 = neg1 >> 1; // -8  
    bitset<16> bn2{neg2};  
    cout << bn2 << endl;  // 1111111111111000  
  
    short neg3 = neg1 >> 2; // -4  
    bitset<16> bn3{neg3};  
    cout << bn3 << endl;  // 1111111111111100  
  
    short neg4 = neg1 >> 4; // -1  
    bitset<16> bn4{neg4};      
    cout << bn4 << endl;  // 1111111111111111  
  
    short neg5 = neg1 >> 5; // -1   
    bitset<16> bn5{neg5};      
    cout << bn5 << endl;  // 1111111111111111  
}  
```  
  
## <a name="shifts-and-promotions"></a>시프트 및 확장  
 시프트 연산자 양쪽에 있는 식은 정수 계열 형식이어야 합니다. 정수 계열 확장에 설명 된 규칙에 따라 수행 됩니다 [표준 변환](standard-conversions.md)합니다. 결과 형식은 확장 된 유형의와 같습니다 *shift 식*합니다.  
  
 다음 예제에서는 형식 `char`의 변수가 `int`로 확장됩니다.  
  
```cpp  
#include <iostream>  
#include <typeinfo>  
  
using namespace std;  
  
int main() {  
    char char1 = 'a';  
  
    auto promoted1 = char1 << 1;   // 194  
    cout << typeid(promoted1).name() << endl;  // int  
  
    auto promoted2 = char1 << 10;  // 99328  
    cout << typeid(promoted2).name() << endl;  // int  
}  
```  
  
## <a name="additional-details"></a>추가 정보  
 경우 시프트 연산의 결과가 정의 되지 않습니다 *덧셈 식* 가 음수 이거나 *덧셈 식* 보다 크거나 (승격)의 비트 수와 같고  *shift 식*합니다. 없음 시프트 연산이 수행 됩니다 *덧셈 식* 은 0입니다.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned int int1 = 4;  
    bitset<32> b1{int1};  
    cout << b1 << endl;    // 00000000000000000000000000000100  
  
    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior  
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior  
  
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int6 = int1 << 0;  
    bitset<32> b6{int6};  
    cout << b6 << endl;    // 00000000000000000000000000000100 (no change)}  
}  
```  
  
## <a name="footnotes"></a>각주  
 1 다음은 시프트 연산자는 C + + 11 ISO 사양 (INCITS/ISO/IEC 14882-2011[2012]), 단원 5.8.2 및 5.8.3에에서 설명.  
  
 값 **E1 << E2** 은 **E1** 왼쪽 이동 **E2** 비트 위치; 비워진 비트는 0으로 채워집니다. 경우 **E1** 부호 없는 형식 결과의 값은 **E1 × 2**<sup>**E2**</sup>감소에 표시할 수 있는 최대 값 보다 하나 더 큰 모듈로, 결과 형식입니다. 그렇지 않은 경우, **E1** 이 부호 있는 형식이 고 음수가 아닌 값 및 **E1 × 2**<sup>**E2** </sup> 가 해당 부호 없는 형식으로 표현 결과 형식의 다음 결과 형식으로 변환 하 고 해당 값을은 결과 값이입니다. 그렇지 않으면 동작이 정의 되지 않습니다.  
  
 값 **E1 >> E2** 은 **E1** 오른쪽 이동 된 **E2** 비트 위치입니다. 경우 **E1** 부호 없는 형식 이거나 **E1** 이 부호 있는 형식이 고 음수가 아닌 값으로, 결과의 몫의 정수 부분은 **E1/2** <sup> **E2**</sup>합니다. 경우 **E1** 에 음수 값이 부호 있는 형식, 구현에서 정의 된 결과 값이 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [이항 연산자가 있는 식](../cpp/expressions-with-binary-operators.md)   
 [C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)