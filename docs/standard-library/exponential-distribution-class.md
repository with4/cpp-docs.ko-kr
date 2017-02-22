---
title: "exponential_distribution 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::exponential_distribution"
  - "exponential_distribution"
  - "tr1::exponential_distribution"
  - "tr1.exponential_distribution"
  - "random/std::tr1::exponential_distribution"
  - "std.tr1.exponential_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exponential_distribution 클래스"
  - "exponential_distribution 클래스[TR1]"
ms.assetid: d54f3126-a09b-45f9-a30b-0d94d03bcdc9
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# exponential_distribution 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지수 분포를 생성합니다.  
  
## 구문  
  
```  
template<class RealType = double> class exponential_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructors and reset functions     explicit exponential_distribution(RealType lambda = 1.0);     explicit exponential_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     RealType lambda() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 매개 변수  
 `RealType`  
 부동 소수점 결과 형식으로, 기본적으로 `double`로 지정되어 있습니다.  가능한 형식은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 지수 분포에 따라 분포된 경우 템플릿 클래스는 사용자 지정 정수 형식 또는 아무 것도 제공되지 않았다면 `double` 형식의 값을 생성하는 분포를 설명합니다.  다음 테이블은 개별 멤버에 대한 문서와 연결되어 있습니다.  
  
||||  
|-|-|-|  
|[exponential\_distribution::exponential\_distribution](../Topic/exponential_distribution::exponential_distribution.md)|`exponential_distribution::lambda`|`exponential_distribution::param`|  
|`exponential_distribution::operator()`||[exponential\_distribution::param\_type](../Topic/exponential_distribution::param_type.md)|  
  
 속성 함수 `lambda()`은 저장된 분포 매개 변수 `lambda`의 값을 반환합니다.  
  
 분포 클래스 및 이러한 클래스의 멤버에 대한 자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
 지수 분포에 대한 자세한 내용은 Wolfram MathWorld 문서 [지수 분포](http://go.microsoft.com/fwlink/?LinkId=401098)를 참조하세요.  
  
## 예제  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double l, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::exponential_distribution<> distr(l);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "lambda() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.lambda() << std::endl;  
  
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
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double l_dist = 0.5;  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): ";  
    std::cin >> l_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(l_dist, samples);  
}  
  
```  
  
## 출력  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
  
min() == 0  
max() == 1.79769e+308  
lambda() == 1.0000000000  
Distribution for 10 samples:  
          1:   0.0936880533  
          2:   0.1225944894  
          3:   0.6443593183  
          4:   0.6551171649  
          5:   0.7313457551  
          6:   0.7313557977  
          7:   0.7590097389  
          8:   1.4466885214  
          9:   1.6434088411  
         10:   2.1201210996  
```  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)