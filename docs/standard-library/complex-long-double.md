---
title: "complex&lt;long double&gt; | Microsoft Docs"
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
  - "std::complex<long double>"
  - "complex<long double>"
  - "std.complex<long double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex<long double> 함수"
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
caps.latest.revision: 20
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# complex&lt;long double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

둘 다 형식이 `long double`인 개체의 정렬된 쌍을 저장하는 개체를 설명합니다. 첫 번째 개체는 복소수의 실수 부분을 나타내고 두 번째 개체는 허수 부분을 나타냅니다.  
  
## 구문  
  
```  
template<>  
   class complex<long double> {  
public:  
   constexpr complex(  
      long double _RealVal = 0,   
      long double _ImagVal = 0  
   );  
complex(  
      constexpr complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### 매개 변수  
 `_RealVal`  
 생성되고 있는 복소수의 실수 부분에 대한 **long double**  형식의 값입니다.  
  
 `_ImagVal`  
 생성되고 있는 복소수의 허수 부분에 대한 `long double` 형식의 값입니다.  
  
 `_ComplexNum`  
 생성되고 있는 `long double` 형식의 복소수를 초기화하기 위해 사용되는 실수 부분과 허수 부분으로 이루어진 **double** 또는 **float** 형식의 복소수입니다.  
  
## 반환 값  
 `long double` 형식의 복소수입니다.  
  
## 설명  
 `long double` 형식의 complex 클래스에 대한 템플릿 클래스 complex의 명시적 특수화는 그것이 정의하는 생성자에서만 템플릿 클래스와 다릅니다.  `long double`에서 **float**로의 변환은 암시적일 수 있지만 **double**에서 `long double`로의 변환은 **명시적**이어야 합니다.  **명시적**의 사용은 할당 구문을 사용하는 형식 변환의 시작을  배제합니다.  
  
 템플릿 클래스 `complex`에 대한 자세한 내용은 [complex 클래스](../standard-library/complex-class.md)를 참조하세요.  템플릿 클래스 `complex`의 멤버 목록은 다음을 참조하세요.  
  
## 예제  
  
```  
// complex_comp_ld.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <long double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type float gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 1.0 , 3.0 );  
   complex <long double> c2longdouble ( c2float );  
   cout << "Implicit conversion from type float to type long double,"  
        << "\n gives c2longdouble = " << c2longdouble << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type double  
   complex <double> c3double ( 3.0 , 4.0 );  
   complex <long double> c3longdouble ( c3double );  
   cout << "Implicit conversion from type long double to type float,"  
        << "\n gives c3longdouble = " << c3longdouble << endl;  
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3longdouble );  
   double argc3 = arg ( c3longdouble );  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
```  
  
  **Specifying initial real & imaginary parts,**  
 **as type float gives c1 \= \(4,5\)**  
**Implicit conversion from type float to type long double,**  
 **gives c2longdouble \= \(1,3\)**  
**Implicit conversion from type long double to type float,**  
 **gives c3longdouble \= \(3,4\)**  
**The modulus of c3 is recovered from c3 using: abs \( c3 \) \= 5**  
**Argument of c3 is recovered from c3 using:**  
 **arg \( c3 \) \= 0.927295 radians, which is 53.1301 degrees.**   
## 요구 사항  
 **헤더**: \<complex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [complex 클래스](../standard-library/complex-class.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)