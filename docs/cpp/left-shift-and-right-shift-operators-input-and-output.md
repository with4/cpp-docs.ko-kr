---
title: "왼쪽 시프트 및 오른쪽 시프트 연산자(&gt;&gt; 및 &lt;&lt;) | Microsoft Docs"
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
  - "<<"
  - ">>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<< 연산자, 특정 개체와 사용"
  - ">> 연산자"
  - "비트 시프트 연산자"
  - "왼쪽 시프트 연산자"
  - "연산자[C++], 시프트"
  - "오른쪽 시프트 연산자"
  - "시프트 연산자"
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 왼쪽 시프트 및 오른쪽 시프트 연산자(&gt;&gt; 및 &lt;&lt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비트 시프트 연산자는 `>>`의 비트를 오른쪽으로 이동하는 오른쪽 시프트 연산자\(`shift_expression`\)와 `<<`의 비트를 왼쪽으로 이동하는 왼쪽 시프트 연산자\(`shift_expression`\)입니다.  <sup>1</sup>  
  
## 구문  
  
```  
  
        shift-expression << additive-expression  
shift-expression >> additive-expression  
```  
  
## 설명  
  
> [!IMPORTANT]
>  다음 설명 및 예제는 X86 및 x64 아키텍처용 Windows에 대해 유효합니다.  왼쪽 시프트 및 오른쪽 시프트 연산자를 구현하는 방법은 ARM 장치용 Windows RT에서는 상당히 다릅니다.  자세한 내용은 [Hello ARM](http://blogs.msdn.com/b/vcblog/archive/2012/10/25/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c.aspx) 블로그 게시물의 "시프트 연산자" 섹션을 참조하세요.  
  
## 왼쪽 시프트  
 왼쪽 시프트 연산자를 사용하면 `shift-expression`의 비트가 `additive-expression`에 의해 지정된 위치의 수만큼 왼쪽으로 이동합니다.  시프트 연산으로 비워진 비트 위치는 0으로 채워집니다.  왼쪽 시프트는 논리 시프트입니다\(부호 비트를 포함해 끝에서 벗어나 이동한 비트는 무시됨\).  비트 시프트에 대한 자세한 내용은 [비트 시프트](http://en.wikipedia.org/wiki/Bitwise_shift)를 참조하세요.  
  
 다음 예제에서는 부호 없는 숫자를 사용하는 왼쪽 시프트 연산을 보여 줍니다.  예제에서는 값을 비트 집합으로 나타내어 비트에서 어떤 일이 발생하는지 보여 줍니다.  자세한 내용은 [bitset 클래스](../standard-library/bitset-class.md)을 참조하세요.  
  
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
  
 부호 비트가 영향을 받도록 부호 있는 숫자를 왼쪽 시프트하면 결과가 정의되지 않습니다.  다음 예제에서는 1비트가 부호 비트 위치로 왼쪽 이동하면 Visual C\+\+에서 어떤 일이 발생하는지 보여 줍니다.  
  
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
  
## 오른쪽 시프트  
 오른쪽 시프트 연산자를 사용하면 `shift-expression`의 비트 패턴이 `additive-expression`에 의해 지정된 위치의 수만큼 오른쪽으로 이동합니다.  부호 없는 숫자의 경우 시프트 연산으로 비워진 비트 위치는 0으로 채워집니다.  부호 있는 숫자의 경우 부호 비트는 비워진 비트 위치를 채우는 데 사용됩니다.  즉, 숫자가 양수이면 0이 사용되고 숫자가 음수이면 1이 사용됩니다.  
  
> [!IMPORTANT]
>  부호 있는 음수의 오른쪽 시프트 결과는 구현에 따라 다릅니다.  Visual C\+\+는 부호를 사용하여 비워진 비트 위치를 채우지만 다른 구현도 마찬가지라는 보장은 없습니다.  
  
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
  
## 시프트 및 확장  
 시프트 연산자 양쪽에 있는 식은 정수 계열 형식이어야 합니다.  정수 계열 확장은 [정수 계열 확장](../misc/integral-promotions.md)에 설명된 규칙에 따라 수행됩니다.  결과 형식은 확장된 `shift-expression`의 형식과 같습니다.  
  
 다음 예제에서는 형식 `char`의 변수가 `int`로 확장됩니다.  
  
```cpp  
#include <iostream>  
#include <typeinfo>  
  
using namespace std;  
  
int main() {  
    char char1 = 'a';  
  
    auto promoted1 = char1 << 1;  // 194  
    cout << typeid(promoted1).name() << endl;  // int  
  
    auto promoted2 = char1 << 10;  // 99328  
    cout << typeid(promoted2).name() << endl;   // int  
}  
```  
  
## 추가 정보  
 `additive-expression`이 음수이거나 `additive-expression`이 \(확장된\) `shift-expression`의 비트 수보다 크거나 같은 경우 시프트 연산의 결과가 정의되지 않습니다.  `additive-expression`이 0이면 시프트 연산이 수행되지 않습니다.  
  
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
  
## 각주  
 1 다음은 C\+\+ ISO 사양\(INCITS\/ISO\/IEC 14882\-2011\[2012\]\), 단원 5.8.2 및 5.8.3의 시프트 연산자에 대한 설명입니다.  
  
 `E1 << E2`의 값은 `E1` 왼쪽 이동된 `E2` 비트 위치입니다. 비워진 비트는 0으로 채워집니다.  `E1`이 부호 없는 형식이면 결과의 값은 `E1 × 2`<sup>E2</sup>이고 줄어든 나머지는 결과 형식에 나타낼 수 있는 최대 값보다 1이 큽니다.  그렇지 않으면 `E1`이 부호 있는 형식이고 음수가 아닌 값이고 `E1 × 2`<sup>E2</sup>가 해당 부호 없는 형식의 결과 형식에 나타낼 수 있는 경우 결과 형식으로 변환된 그 값은 결과 값입니다. 그렇지 않으면 동작이 정의되지 않습니다.  
  
 `E1 >> E2`의 값은 `E1` 오른쪽 이동된 `E2` 비트 위치입니다.  `E1`이 부호 없는 형식이거나 `E1`이 부호 있는 형식이고 음수가 아닌 값인 경우 결과의 값은 `E1/2`<sup>E2</sup> 몫의 정수 부분입니다.  `E1`이 부호 있는 형식이고 음수인 경우 결과 값은 구현 시 정의됩니다.  
  
## 참고 항목  
 [이항 연산자로 구성된 식](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)