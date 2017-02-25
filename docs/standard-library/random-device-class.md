---
title: "random_device 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "random_device"
  - "random/std::tr1::random_device"
  - "tr1.random_device"
  - "std::tr1::random_device"
  - "std.tr1.random_device"
  - "tr1::random_device"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "random_device 클래스"
  - "random_device 클래스[TR1]"
ms.assetid: 4393d515-0cb6-4e0d-a2ba-c780f05dc1bf
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# random_device 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

외부 장치에서 임의 시퀀스를 생성합니다.  
  
## 구문  
  
```  
class random_device { public:     typedef unsigned int result_type;     // cosntructor     explicit random_device(const std::string& token = "");     // properties     static result_type min();     static result_type max();     double entropy() const;     // generate     result_type operator()();     // no-copy functions     random_device(const random_device&) = delete;     void operator=(const random_device&) = delete; };  
```  
  
## 멤버  
  
|||  
|-|-|  
|[random\_device::random\_device](../Topic/random_device::random_device.md)|[random\_device::entropy](../Topic/random_device::entropy.md)|  
|[random\_device::operator\(\)](../Topic/random_device::operator\(\).md)||  
  
## 설명  
 이 클래스는 난수의 소스를 설명하고 ISO C\+\+ 표준에 따라 명확하지 않거나 안전을 위해 암호화하는 것이 허용되지만 그럴 필요는 없습니다.  Visual Studio 구현 시 생성된 값은 명확하지 않거나 암호화되지만 엔진 및 엔진 어댑터\(예: 대부분의 응용 프로그램에 선택되는 빠른 고품질 엔진인 [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md)\)에서 생성된 생성기보다 훨씬 느리게 실행됩니다.  
  
 `random_device` 결과는 닫힌 범위 \[`0, 2`<sup>32</sup>\) 내에서 균일하게 분포됩니다.  
  
 `random_device`는 비블로킹 호출이 수행되지 않을 수도 있습니다.  
  
 일반적으로 `random_device`는 엔진 또는 엔진 어댑터를 통해 생성된 다른 생성기를 시드하는 데 사용됩니다.  자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하십시오.  
  
## 예제  
 다음 코드는 이 클래스의 기본 기능과 예제 결과를 보여줍니다.  `random_device`의 명확하지 않은 특성 때문에 **출력** 섹션에 표시된 난수 값은 사용자의 결과와 일치하지 않을 것입니다.  이는 정상적이며 예상된 결과입니다.  
  
```cpp  
// random_device_engine.cpp   
// cl.exe /W4 /nologo /EHsc /MTd   
#include <random>   
#include <iostream>   
using namespace std;  
  
int main()   
{   
    random_device gen;   
  
    cout << "entropy == " << gen.entropy() << endl;   
    cout << "min == " << gen.min() << endl;   
    cout << "max == " << gen.max() << endl;   
  
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
}  
```  
  
 **출력:**  
  
  **entropy \=\= 32**  
**min \=\= 0**  
**max \=\= 4294967295**  
**10개 난수 값**  
**4183829181**  
**1454391608**  
**1176278697**  
**2468830096**  
**3959347222**  
**1803123400**  
**1339590545**  
**1304896877**  
**604088490**  
**2293276253** 이 예제는 간단한 예제로 이러한 생성기의 일반적인 사용 사례를 대표적으로 보여주지는 않습니다.  보다 대표적인 코드 예제는 [\<random\>](../standard-library/random.md)를 참조하세요.  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)