---
title: "negative_binomial_distribution 클래스 | Microsoft Docs"
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
  - "tr1::negative_binomial_distribution"
  - "tr1.negative_binomial_distribution"
  - "std.tr1.negative_binomial_distribution"
  - "random/std::tr1::negative_binomial_distribution"
  - "std::tr1::negative_binomial_distribution"
  - "negative_binomial_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "negative_binomial_distribution 클래스"
ms.assetid: 7f5f0967-7fdd-4578-99d4-88f292b4fe9c
caps.latest.revision: 15
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# negative_binomial_distribution 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

음이항 분포를 생성합니다.  
  
## 구문  
  
```  
template<class IntType = int> class negative_binomial_distribution { public:     // types     typedef IntType result_type;     struct param_type;     // constructor and reset functions     explicit negative_binomial_distribution(IntType k = 1, double p = 0.5);     explicit negative_binomial_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     IntType k() const;     double p() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 매개 변수  
 `IntType`  
 정수 결과 형식으로, 기본적으로 `int`로 지정되어 있습니다.  가능한 형식은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 음이항 분포 이산 확률 함수에 따라 분포된 경우 템플릿 클래스는 사용자 지정 정수 형식 또는 아무 것도 제공되지 않았다면 `int` 형식의 값을 생성하는 분포를 설명합니다.  다음 테이블은 개별 멤버에 대한 문서와 연결되어 있습니다.  
  
||||  
|-|-|-|  
|[negative\_binomial\_distribution::negative\_binomial\_distribution](../Topic/negative_binomial_distribution::negative_binomial_distribution.md)|`negative_binomial_distribution::k`|`negative_binomial_distribution::param`|  
|`negative_binomial_distribution::operator()`|`negative_binomial_distribution::p`|[negative\_binomial\_distribution::param\_type](../Topic/negative_binomial_distribution::param_type.md)|  
  
 속성 멤버 `k()` 및 `p()`는 각각 현재 저장된 분포 매개 변수 값 `k` 및 `p`를 반환합니다.  
  
 분포 클래스 및 이러한 클래스의 멤버에 대한 자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
 음이항 분포 이산 확률 함수에 대한 자세한 내용은 Wolfram MathWorld 문서 [음이항 분포](http://go.microsoft.com/fwlink/?LinkId=400516)를 참조하세요.  
  
## 예제  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const int k, const double p, const int& s) {  
  
    // uncomment to use a non-deterministic seed  
    //    std::random_device rd;  
    //    std::mt19937 gen(rd());  
    std::mt19937 gen(1729);  
  
    std::negative_binomial_distribution<> distr(k, p);  
  
    std::cout << std::endl;  
    std::cout << "k == " << distr.k() << std::endl;  
    std::cout << "p == " << distr.p() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Histogram for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    int    k_dist = 1;  
    double p_dist = 0.5;  
    int    samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter an integer value for k distribution (where 0 < k): ";  
    std::cin >> k_dist;  
    std::cout << "Enter a double value for p distribution (where 0.0 < p <= 1.0): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for a sample count: ";  
    std::cin >> samples;  
  
    test(k_dist, p_dist, samples);  
}  
  
```  
  
## 출력  
 첫 번째 실행:  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for k distribution (where 0 < k): 1  
Enter a double value for p distribution (where 0.0 < p <= 1.0): .5  
Enter an integer value for a sample count: 100  
  
k == 1  
p == 0.5  
Histogram for 100 samples:  
    0 :::::::::::::::::::::::::::::::::::::::::::  
    1 ::::::::::::::::::::::::::::::::  
    2 ::::::::::::  
    3 :::::::  
    4 ::::  
    5 ::  
```  
  
 두 번째 실행:  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter an integer value for k distribution (where 0 < k): 100  
Enter a double value for p distribution (where 0.0 < p <= 1.0): .667  
Enter an integer value for a sample count: 100  
  
k == 100  
p == 0.667  
Histogram for 100 samples:  
   31 ::  
   32 :  
   33 ::  
   34 :  
   35 ::  
   37 ::  
   38 :  
   39 :  
   40 ::  
   41 :::  
   42 :::  
   43 :::::  
   44 :::::  
   45 ::::  
   46 ::::::  
   47 ::::::::  
   48 :::  
   49 :::  
   50 :::::::::  
   51 :::::::  
   52 ::  
   53 :::  
   54 :::::  
   56 ::::  
   58 :  
   59 :::::  
   60 ::  
   61 :  
   62 ::  
   64 :  
   69 ::::  
```  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)