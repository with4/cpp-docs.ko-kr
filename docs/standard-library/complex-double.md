---
title: complex&lt;double&gt; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: complex/std::complex<double>
dev_langs: C++
helpviewer_keywords: complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b279b78c309dd9fff87954d9b50b255b7f0d9f25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="complexltdoublegt"></a>complex&lt;double&gt;
둘 다 형식이 **double***,*인 개체의 정렬된 쌍을 저장하는 개체를 설명합니다. 첫 번째 개체는 복소수의 실수부를 나타내고 두 번째 개체는 허수부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template <>
class complex<double> {
public:
    constexpr complex(
    double RealVal = 0,
    double ImagVal = 0);

constexpr complex(const complex<double>& complexNum);

constexpr explicit complex(const complex<long double>& complexNum);
// rest same as template class complex
};
```  
  
#### <a name="parameters"></a>매개 변수  
 `RealVal`  
 생성되는 복소수의 실수부에 대한 **double** 형식의 값입니다.  
  
 `ImagVal`  
 생성되는 복소수의 허수부에 대한 **double** 형식의 값입니다.  
  
 `complexNum`  
 생성되는 **double** 형식의 복소수를 초기화하기 위해 사용되는 실수부와 허수부로 이루어진 **float** 또는 `long double` 형식의 복소수입니다.  
  
## <a name="return-value"></a>반환 값  
 **double** 형식의 복소수입니다.  
  
## <a name="remarks"></a>설명  
 **double** 형식의 complex 클래스에 대한 템플릿 클래스 complex의 명시적 특수화는 해당 특수화가 정의하는 생성자에서만 템플릿 클래스와 다릅니다. **float**에서 **double**로의 변환은 암시적일 수 있지만 `long double`에서 **double**로의 변환은 **명시적**이어야 합니다. **명시적**의 사용은 할당 구문을 사용하는 형식 변환의 시작을 배제합니다.  
  
 템플릿 클래스 `complex`에 대한 자세한 내용은 [complex 클래스](../standard-library/complex-class.md)를 참조하세요. 템플릿 클래스 `complex`의 멤버 목록은 다음을 참조하세요.  
  
## <a name="example"></a>예  
  
```cpp  
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
\* Output:   
Specifying initial real & imaginary parts,  
 as type double gives c1 = (4,5)  
Implicit conversion from type float to type double,  
 gives c2double = (4,5)  
Explicit conversion from type float to type double,  
 gives c3longdouble = (4,5)  
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 6.40312  
Argument of c3 is recovered from c3 using:  
 arg ( c3 ) = 0.896055 radians, which is 51.3402 degrees.  
*\  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: \<complex>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [complex 클래스](../standard-library/complex-class.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)



