---
title: "uniform_real_distribution 클래스 | Microsoft Docs"
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
  - "tr1::uniform_real_distribution"
  - "std::tr1::uniform_real_distribution"
  - "random/std::tr1::uniform_real_distribution"
  - "uniform_real_distribution"
  - "std.tr1.uniform_real_distribution"
  - "tr1.uniform_real_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uniform_real_distribution 클래스"
ms.assetid: 5cf906fd-0319-4984-b21b-98425cd7532d
caps.latest.revision: 18
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# uniform_real_distribution 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

시작 범위는 포함되고 끝 범위는 제외되는 출력 범위 내에서 균등한\(모든 값이 균일하게 있을 것 같음\) 부동 소수점 분포를 생성합니다.  
  
## 구문  
  
```  
template<class RealType = double> class uniform_real_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructors and reset functions     explicit uniform_real_distribution(RealType a = 0.0, RealType b = 1.0);     explicit uniform_real_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     result_type a() const;     result_type b() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 매개 변수  
 `RealType`  
 부동 소수점 결과 형식으로, 기본적으로 `double`로 지정되어 있습니다.  가능한 형식은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 템플릿 클래스는 분포를 사용하여 사용자 지정 정수 부동 소수점 형식의 값을 생성하는 포함\-제외 분포를 설명합니다. 따라서 모든 값이 균일할 수 있습니다.  다음 테이블은 개별 멤버에 대한 문서와 연결되어 있습니다.  
  
||||  
|-|-|-|  
|[uniform\_real\_distribution::uniform\_real\_distribution](../Topic/uniform_real_distribution::uniform_real_distribution.md)|`uniform_real_distribution::a`|`uniform_real_distribution::param`|  
|`uniform_real_distribution::operator()`|`uniform_real_distribution::b`|[uniform\_real\_distribution::param\_type](../Topic/uniform_real_distribution::param_type.md)|  
  
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
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::uniform_real_distribution<> distr(a,b);  
  
    std::cout << "lower bound == " << distr.a() << std::endl;  
    std::cout << "upper bound == " << distr.b() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "   
            << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 1.0;  
    double b_dist = 1.5;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the lower bound of the distribution: ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the upper bound of the distribution: ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## 출력  
  **Ctrl\+Z를 사용하여 데이터 입력을 건너뛰고 기본값을 사용하여 실행합니다.  분포의 하한으로 부동 소수점 값 0.5를 입력합니다.**  
**분포의 상한으로 부동 소수점 값 1을 입력합니다.**  
**샘플 계산을 위해 정수 값 20을 입력합니다.**  
**하한 \=\= 0.5**  
**하한 \=\= 1**  
**20개 표본의 분포:**  
 **1: 0.5144304741**  
 **2: 0.6003997192**  
 **3: 0.6060792968**  
 **4: 0.6270416650**  
 **5: 0.6295091197**  
 **6: 0.6437749373**  
 **7: 0.6513740058**  
 **8: 0.7062379346**  
 **9: 0.7117609406**  
 **10: 0.7206888566**  
 **11: 0.7423223702**  
 **12: 0.7826033033**  
 **13: 0.8112872958**  
 **14: 0.8440467608**  
 **15: 0.8461254641**  
 **16: 0.8598305065**  
 **17: 0.8640874069**  
 **18: 0.8770968361**  
 **19: 0.9397858282**  
 **20: 0.9804645012**    
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)