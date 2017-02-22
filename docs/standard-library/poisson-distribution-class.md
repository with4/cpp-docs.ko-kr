---
title: "poisson_distribution 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "poisson_distribution"
  - "std.tr1.poisson_distribution"
  - "random/std::tr1::poisson_distribution"
  - "std::tr1::poisson_distribution"
  - "tr1.poisson_distribution"
  - "tr1::poisson_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "poisson_distribution 클래스"
  - "poisson_distribution 클래스[TR1]"
ms.assetid: 09614281-349a-45f7-8e95-c0196be0a937
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# poisson_distribution 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

푸아송 분포를 생성합니다.  
  
## 구문  
  
```  
template<class IntType = int> class poisson_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructors and reset functions     explicit poisson_distribution(double mean = 1.0);     explicit poisson_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     double mean() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 매개 변수  
 `IntType`  
 정수 결과 형식으로, 기본적으로 `int`로 지정되어 있습니다.  가능한 형식은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 템플릿 클래스는 푸아송 분포를 사용하여 사용자 지정 정수 형식의 값을 생성하는 분포를 설명합니다.  다음 테이블은 개별 멤버에 대한 문서와 연결되어 있습니다.  
  
||||  
|-|-|-|  
|[poisson\_distribution::poisson\_distribution](../Topic/poisson_distribution::poisson_distribution.md)|`poisson_distribution::mean`|`poisson_distribution::param`|  
|`poisson_distribution::operator()`||[poisson\_distribution::param\_type](../Topic/poisson_distribution::param_type.md)|  
  
 속성 함수 `mean()`은 저장된 분포 매개 변수 `mean`의 값을 반환합니다.  
  
 분포 클래스 및 이러한 클래스의 멤버에 대한 자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
 푸아송 분포에 대한 자세한 내용은 Wolfram MathWorld 문서 [푸아송 분포](http://go.microsoft.com/fwlink/?LinkId=401112)를 참조하세요.  
  
## 예제  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double p, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::poisson_distribution<> distr(p);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.mean() << std::endl;  
  
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
    double p_dist = 1.0;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
  
```  
  
## 출력  
 첫 번째 테스트:  
  
  **Ctrl\+Z를 사용하여 데이터 입력을 건너뛰고 기본값을 사용하여 실행합니다.  'mean' 분포 매개 변수의 부동 소수점 값\(0보다 커야 함\) 1을 입력합니다.**  
**샘플 계산을 위해 정수 값 100을 입력합니다.**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 1.0000000000**  
**100개 샘플의 분포:**  
 **0 ::::::::::::::::::::::::::::::**  
 **1 ::::::::::::::::::::::::::::::::::::::**  
 **2 :::::::::::::::::::::::**  
 **3 ::::::::**  
 **5 :**  두 번째 테스트:  
  
  **Ctrl\+Z를 사용하여 데이터 입력을 건너뛰고 기본값을 사용하여 실행합니다.  'mean' 분포 매개 변수의 부동 소수점 값\(0보다 커야 함\) 10을 입력합니다.**  
**샘플 계산을 위해 정수 값 100을 입력합니다.**  
**min\(\) \=\= 0**  
**max\(\) \=\= 2147483647**  
**p\(\) \=\= 10.0000000000**  
**100개 샘플의 분포:**  
 **3 :**  
 **4 ::**  
 **5 ::**  
 **6 ::::::::**  
 **7 ::::**  
 **8 ::::::::**  
 **9 ::::::::::::::**  
 **10 ::::::::::::**  
 **11 ::::::::::::::::**  
 **12 :::::::::::::::**  
 **13 ::::::::**  
 **14 ::::::**  
 **15 :**  
 **16 ::**  
 **17 :**    
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)