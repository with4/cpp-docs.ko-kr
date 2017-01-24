---
title: "piecewise_constant_distribution 클래스 | Microsoft Docs"
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
  - "std.tr1.piecewise_constant_distribution"
  - "tr1.piecewise_constant_distribution"
  - "tr1::piecewise_constant_distribution"
  - "std::tr1::piecewise_constant_distribution"
  - "random/std::tr1::piecewise_constant_distribution"
  - "piecewise_constant_distribution"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "piecewise_constant_distribution 클래스"
ms.assetid: 2c9a21fa-623e-4d63-b827-3f1556b6dedb
caps.latest.revision: 23
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# piecewise_constant_distribution 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 간격의 확률이 균일하고 폭이 다양한 간격이 있는 부분 일정 분포를 생성합니다.  
  
## 구문  
  
```  
template<class RealType = double> class piecewise_constant_distribution { public:     // types     typedef RealType result_type;     struct param_type;     // constructor and reset functions     piecewise_constant_distribution();     template<class InputIteratorI, class InputIteratorW>     piecewise_constant_distribution(InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);     template<class UnaryOperation>     piecewise_constant_distribution(initializer_list<RealType> intervals, UnaryOperation weightfunc);     template<class UnaryOperation>     piecewise_constant_distribution(size_t count, RealType xmin, RealType xmax, UnaryOperation weightfunc);     explicit piecewise_constant_distribution(const param_type& parm);     void reset();     // generating functions     template<class URNG>     result_type operator()(URNG& gen);     template<class URNG>     result_type operator()(URNG& gen, const param_type& parm);     // property functions     vector<result_type> intervals() const;     vector<result_type> densities() const;     param_type param() const;     void param(const param_type& parm);     result_type min() const;     result_type max() const; };  
```  
  
#### 매개 변수  
 `RealType`  
 부동 소수점 결과 형식으로, 기본적으로 `double`로 지정되어 있습니다.  가능한 형식은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 이 표본 분포에는 각 간격의 확률이 균일하고 폭이 다양한 간격이 있습니다.  표본 분포에 대한 자세한 내용은 [piecewise\_linear\_distribution 클래스](../standard-library/piecewise-linear-distribution-class.md) 및 [discrete\_distribution](../standard-library/discrete-distribution-class.md)을 참조하세요.  
  
 다음 테이블은 개별 멤버에 대한 문서와 연결되어 있습니다.  
  
||||  
|-|-|-|  
|[piecewise\_constant\_distribution::piecewise\_constant\_distribution](../Topic/piecewise_constant_distribution::piecewise_constant_distribution.md)|`piecewise_constant_distribution::intervals`|`piecewise_constant_distribution::param`|  
|`piecewise_constant_distribution::operator()`|`piecewise_constant_distribution::densities`|[piecewise\_constant\_distribution::param\_type](../Topic/piecewise_constant_distribution::param_type.md)|  
  
 속성 함수 `intervals()`는 저장된 분포 간격 집합과 함께 `vector<RealType>`을 반환합니다.  
  
 속성 함수 `densities()`는 각 간격 집합에 대해 저장된 밀도와 함께 `vector<RealType>`을 반환합니다. 이러한 밀도는 생성자 매개 변수에서 제공하는 가중치에 따라 계산됩니다.  
  
 분포 클래스 및 이러한 클래스의 멤버에 대한 자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 예제  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
using namespace std;  
  
void test(const int s) {  
  
    // uncomment to use a non-deterministic generator  
    // random_device rd;  
    // mt19937 gen(rd());  
    mt19937 gen(1701);  
  
    // Three intervals, non-uniform: 0 to 1, 1 to 6, and 6 to 15  
    vector<double> intervals{ 0, 1, 6, 15 };  
    // weights determine the densities used by the distribution  
    vector<double> weights{ 1, 5, 10 };  
  
    piecewise_constant_distribution<double> distr(intervals.begin(), intervals.end(), weights.begin());  
  
    cout << endl;  
    cout << "min() == " << distr.min() << endl;  
    cout << "max() == " << distr.max() << endl;  
    cout << "intervals (index: interval):" << endl;  
    vector<double> i = distr.intervals();  
    int counter = 0;  
    for (const auto& n : i) {  
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;  
        ++counter;  
    }  
    cout << endl;  
    cout << "densities (index: density):" << endl;  
    vector<double> d = distr.densities();  
    counter = 0;  
    for (const auto& n : d) {  
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;  
        ++counter;  
    }  
    cout << endl;  
  
    // generate the distribution as a histogram  
    map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    cout << "Distribution for " << s << " samples:" << endl;  
    for (const auto& elem : histogram) {  
        cout << setw(5) << elem.first << '-' << elem.first+1 << ' ' << string(elem.second, ':') << endl;  
    }  
    cout << endl;  
}  
  
int main()  
{  
    int samples = 100;  
  
    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;  
    cout << "Enter an integer value for the sample count: ";  
    cin >> samples;  
  
    test(samples);  
}  
  
```  
  
## 출력  
  **Ctrl\+Z를 사용하여 데이터 입력을 건너뛰고 기본값을 사용하여 실행합니다.  샘플 계산을 위해 정수 값 100을 입력합니다.**  
**min\(\) \=\= 0**  
**max\(\) \=\= 15**  
**intervals \(index: interval\):**  
 **0:   0.0000000000**  
 **1:   1.0000000000**  
 **2:   6.0000000000**  
 **3:  15.0000000000**  
**densities \(index: density\):**  
 **0:   0.0625000000**  
 **1:   0.0625000000**  
 **2:   0.0694444444**  
**100개 샘플의 분포:**  
 **0\-1 :::::::**  
 **1\-2 ::::::**  
 **2\-3 :::::**  
 **3\-4 ::::::**  
 **4\-5 :::::::**  
 **5\-6 ::::::**  
 **6\-7 :::**  
 **7\-8 ::::::::::**  
 **8\-9 ::::::**  
 **9\-10 ::::::::::::**  
 **10\-11 :::::**  
 **11\-12 ::::::**  
 **12\-13 :::::::::**  
 **13\-14 ::::**  
 **14\-15 ::::::::**    
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)   
 [piecewise\_linear\_distribution](../standard-library/piecewise-linear-distribution-class.md)