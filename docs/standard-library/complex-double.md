---
title: "complex&lt;double&gt; | Microsoft Docs"
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
  - "std.complex<double>"
  - "complex<double>"
  - "std::complex<double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "복잡 한 < 더블 > 함수"
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# complex&lt;double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

둘 다 형식이 **double***인 개체의 정렬된 쌍을 저장하는 개체를 설명합니다.* 첫 번째 개체는 복소수의 실수 부분을 나타내고 두 번째 개체는 허수 부분을 나타냅니다.  
  
## 구문  
  
```  
template<>  
   class complex<double> {  
public:  
   constexpr complex(  
      double _RealVal = 0,   
      double _ImagVal = 0  
   );  
  
   constexpr complex(  
      const complex<double>& _ComplexNum  
   );  
   constexpr explicit complex(  
      const complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### 매개 변수  
 `_RealVal`  
 생성되고 있는 복소수의 실수 부분에 대한 **double** 형식의 값입니다.  
  
 `_ImagVal`  
 생성되고 있는 복소수의 허수 부분에 대한 **double** 형식의 값입니다.  
  
 `_ComplexNum`  
 생성되고 있는 **double** 형식의 복소수를 초기화하기 위해 사용되는 실수 부분과 허수 부분으로 이루어진 **float** 또는 `long double` 형식의 복소수입니다.  
  
## 반환 값  
 **double** 형식의 복소수입니다.  
  
## 설명  
 **double** 형식의 complex 클래스에 대한 템플릿 클래스 complex의 명시적 특수화는 그것이 정의하는 생성자에서만 템플릿 클래스와 다릅니다.**float**에서 **double**로의 변환은 암시적일 수 있지만 `long double`에서 **double**로의 변환은 **명시적**이어야 합니다.**명시적**의 사용은 할당 구문을 사용하는 형식 변환의 시작을  배제합니다.  
  
 템플릿 클래스에 대 한 자세한 내용은 `complex`, 참조 [complex 클래스](../standard-library/complex-class.md)합니다. 템플릿 클래스 `complex`의 멤버 목록은 다음을 참조하세요.  
  
## 예제  
  
```  
// complex_comp_dbl.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type double gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 4.0 , 5.0 );  
   complex <double> c2double ( c2float );  
   cout << "Implicit conversion from type float to type double,"  
        << "\n gives c2double = " << c2double << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type long double  
   complex <long double> c3longdouble ( 4.0 , 5.0 );  
   complex <double> c3double ( c3longdouble );  
   cout << "Explicit conversion from type float to type double,"  
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
  
 **초기 실수 및 허수 부분을 지정 하 형식 double 제공 c1 \= float 제공 c2double double 형식 \(4,5\) 암시적으로 변환 float 제공 c3longdouble double 형식에서 명시적 변환 \(4,5\) \= \(4, 5\) \= c 3의 모듈러스를 사용 하 여 c 3에서 복구: abs \(c3\) 6.40312 \= c 3의 인수를 사용 하 여 c 3에서 복구: arg \(c3\) \= 0.896055 라디안 51.3402도입니다.**   
## 요구 사항  
 **헤더**: \<complex\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [complex 클래스](../standard-library/complex-class.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)