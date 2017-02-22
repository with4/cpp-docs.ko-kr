---
title: "normal_distribution 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1::normal_distribution"
  - "normal_distribution"
  - "std::tr1::normal_distribution"
  - "random/std::tr1::normal_distribution"
  - "std.tr1.normal_distribution"
  - "tr1.normal_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "normal_distribution 클래스"
  - "normal_distribution 클래스[TR1]"
ms.assetid: bf92cdbd-bc72-4d4a-b588-173d748f0d7d
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# normal_distribution 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정규 분포를 생성합니다.  
  
## 구문  
  
```  
template<class RealType = double> class normal_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructors and reset functions     explicit normal_distribution(RealType mean = 0.0, RealType stddev = 1.0);     explicit normal_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     RealType mean() const;     RealType stddev() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 매개 변수  
 `RealType`  
 부동 소수점 결과 형식으로, 기본적으로 `double`로 지정되어 있습니다.  가능한 형식은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 정규 분포에 따라 분포된 경우 템플릿 클래스는 사용자 지정 정수 형식 또는 아무 것도 제공되지 않았다면 `double` 형식의 값을 생성하는 분포를 설명합니다.  다음 테이블은 개별 멤버에 대한 문서와 연결되어 있습니다.  
  
||||  
|-|-|-|  
|[normal\_distribution::normal\_distribution](../Topic/normal_distribution::normal_distribution.md)|`normal_distribution::mean`|`normal_distribution::param`|  
|`normal_distribution::operator()`|`normal_distribution::stddev`|[normal\_distribution::param\_type](../Topic/normal_distribution::param_type.md)|  
  
 속성 함수 `mean()` 및 `stddev()`은 저장된 분포 매개 변수인 `mean` 및 `stddev` 각각에 대한 값을 반환합니다.  
  
 분포 클래스 및 이러한 클래스의 멤버에 대한 자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
 정규 분포에 대한 자세한 내용은 Wolfram MathWorld 문서 [정규 분포](http://go.microsoft.com/fwlink/?LinkId=400924)를 참조하세요.  
  
## 예제  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
using namespace std;  
  
void test(const double m, const double s, const int samples) {  
  
    // uncomment to use a non-deterministic seed  
    //    random_device gen;  
    //    mt19937 gen(rd());  
    mt19937 gen(1701);  
  
    normal_distribution<> distr(m, s);  
  
    cout << endl;  
    cout << "min() == " << distr.min() << endl;  
    cout << "max() == " << distr.max() << endl;  
    cout << "m() == " << fixed << setw(11) << setprecision(10) << distr.mean() << endl;  
    cout << "s() == " << fixed << setw(11) << setprecision(10) << distr.stddev() << endl;  
  
    // generate the distribution as a histogram  
    map<double, int> histogram;  
    for (int i = 0; i < samples; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    cout << "Distribution for " << samples << " samples:" << endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        cout << fixed << setw(11) << ++counter << ": "  
            << setw(14) << setprecision(10) << elem.first << endl;  
    }  
    cout << endl;  
}  
  
int main()  
{  
    double m_dist = 1;  
    double s_dist = 1;  
    int samples = 10;  
  
    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;  
    cout << "Enter a floating point value for the 'mean' distribution parameter: ";  
    cin >> m_dist;  
    cout << "Enter a floating point value for the 'stddev' distribution parameter (must be greater than zero): ";  
    cin >> s_dist;  
    cout << "Enter an integer value for the sample count: ";  
    cin >> samples;  
  
    test(m_dist, s_dist, samples);  
}  
  
```  
  
## 출력  
  
```  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'mean' distribution parameter: 0  
Enter a floating point value for the 'stddev' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
  
min() == -1.79769e+308  
max() == 1.79769e+308  
m() == 0.0000000000  
s() == 1.0000000000  
Distribution for 10 samples:  
          1:  -0.8845823965  
          2:  -0.1995761116  
          3:  -0.1162665130  
          4:  -0.0685154932  
          5:   0.0403741461  
          6:   0.1591327792  
          7:   1.0414389924  
          8:   1.5876269426  
          9:   1.6362637713  
         10:   2.7821317338  
```  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)