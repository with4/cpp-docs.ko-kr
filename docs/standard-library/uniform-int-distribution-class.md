---
title: "uniform_int_distribution 클래스 | Microsoft Docs"
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
  - "tr1.uniform_int_distribution"
  - "random/std::tr1::uniform_int_distribution"
  - "uniform_int_distribution"
  - "tr1::uniform_int_distribution"
  - "std.tr1.uniform_int_distribution"
  - "std::tr1::uniform_int_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uniform_int_distribution 클래스"
ms.assetid: a1867dcd-3bd9-4787-afe3-4b62692c1d04
caps.latest.revision: 20
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# uniform_int_distribution 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

시작 범위와 끝 범위가 포함되는 출력 범위 내에서 균등한\(모든 값이 균일하게 있을 것 같음\) 정수 분포를 생성합니다.  
  
## 구문  
  
```  
template<class IntType = int> class uniform_int_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructors and reset functions     explicit uniform_int_distribution(IntType a = 0, IntType b = numeric_limits<IntType>::max());     explicit uniform_int_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     result_type a() const;     result_type b() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 매개 변수  
 `IntType`  
 정수 결과 형식으로, 기본적으로 `int`로 지정되어 있습니다.  가능한 형식은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 템플릿 클래스는 분포를 사용하여 사용자 지정 정수 형식의 값을 생성하는 포함\-포함 분포를 설명합니다. 따라서 모든 값이 균일할 수 있습니다.  다음 테이블은 개별 멤버에 대한 문서와 연결되어 있습니다.  
  
||||  
|-|-|-|  
|[uniform\_int\_distribution::uniform\_int\_distribution](../Topic/uniform_int_distribution::uniform_int_distribution.md)|`uniform_int_distribution::a`|`uniform_int_distribution::param`|  
|`uniform_int_distribution::operator()`|`uniform_int_distribution::b`|[uniform\_int\_distribution::param\_type](../Topic/uniform_int_distribution::param_type.md)|  
  
 속성 멤버 `a()`는 분포의 현재 저장된 최하한을 반환하고 `b()`는 현재 저장된 최상한을 반환합니다.  이 분포 클래스의 경우 최하한과 최상한 값은 [\<random\>](../standard-library/random.md) 항목에서 설명한 공통 속성 함수 `min()` 및 `max()`가 반환한 값과 동일합니다.  
  
 분포 클래스 및 이러한 클래스의 멤버에 대한 자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 예제  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const int a, const int b, const int s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::uniform_int_distribution<> distr(a, b);  
  
    std::cout << "lower bound == " << distr.a() << std::endl;  
    std::cout << "upper bound == " << distr.b() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    int a_dist = 1;  
    int b_dist = 10;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter an integer value for the lower bound of the distribution: ";  
    std::cin >> a_dist;  
    std::cout << "Enter an integer value for the upper bound of the distribution: ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## 출력  
  **Ctrl\+Z를 사용하여 데이터 입력을 건너뛰고 기본값을 사용하여 실행합니다.  분포의 하한으로 정수 값 0을 입력합니다.**  
**분포의 상한으로 정수 값 12를 입력합니다.**  
**샘플 계산을 위해 정수 값 200을 입력합니다.**  
**하한 \=\= 0**  
**하한 \=\= 12**  
**200개 표본의 분포:**  
 **0 :::::::::::::::**  
 **1 :::::::::::::::::::::**  
 **2 ::::::::::::::::::**  
 **3 :::::::::::::::**  
 **4 :::::::**  
 **5 :::::::::::::::::::::**  
 **6 :::::::::::::**  
 **7 ::::::::::**  
 **8 :::::::::::::::**  
 **9 :::::::::::::**  
 **10 ::::::::::::::::::::::**  
 **11 :::::::::::::**  
 **12 :::::::::::::::::**    
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)