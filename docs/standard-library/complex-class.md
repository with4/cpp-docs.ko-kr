---
title: "complex 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- complex
- complex/std::complex::value_type
- complex/std::complex::imag
- complex/std::complex::real
dev_langs:
- C++
helpviewer_keywords:
- complex numbers
- complex class
ms.assetid: d6492e1c-5eba-4bc5-835b-2a88001a5868
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 8f5f401e61aab91d24679ffdc8d796fb9138ee61
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="complex-class"></a>complex 클래스
템플릿 클래스는 **Type** 형식의 두 개체를 저장하는 개체를 설명하며, 한 개체는 복소수의 실수부를 나타내고 다른 개체는 허수부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
 
template <class   
Type>  
class complex  
```  
  
## <a name="remarks"></a>설명  
 **Type** 클래스의 개체:  
  
-   기본 동작과 함께 공용 기본 생성자, 소멸자, 복사 생성자 및 대입 연산자를 포함합니다.  
  
-   정수 또는 부동 소수점 값이 할당되거나 기본 동작을 사용하는 이러한 값에 형식 캐스트될 수 있습니다.  
  
-   필요에 따라 기본 동작으로 부동 소수점 형식을 위해 정의된 산술 연산자 및 수학 함수를 정의합니다.  
  
 특히 복사본 생성과 뒤에 할당이 이어지는 기본 생성 간에는 차이가 없을 수도 있습니다. **Type** 클래스의 개체에 대한 작업 중 예외를 throw하는 작업이 없을 수도 있습니다.  
  
 세 개의 부동 소수점 형식에 대해 템플릿 클래스 complex의 명시적 특수화가 존재합니다. 이 구현에서, 다른 형식의 **Type** 값은 실제 계산을 위해 **double**로 형식 캐스트됩니다. **double** 결과는 **Type** 형식의 저장된 개체에 다시 할당됩니다`.`  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[complex](#complex)|지정된 실수 및 허수 부분을 사용하거나 다른 복소수의 복사본으로 복소수를 생성합니다.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#value_type)|복소수의 실수부와 허수부를 나타내는 데 사용되는 데이터 형식을 표시하는 형식입니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[imag](#imag)|복소수의 허수 구성 요소를 추출합니다.|  
|[real](#real)|복소수의 실수 구성 요소를 추출합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator*=](#op_star_eq)|대상 복소수와 요소를 곱합니다. 요소는 복소수이거나 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.|  
|[operator+=](#op_add_eq)|대상 복소수에 숫자를 더합니다. 여기서 더해지는 숫자는 복소수이거나 대상 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.|  
|[operator-=](#operator-_eq)|대상 복소수에서 숫자를 뺍니다. 여기서 빼는 숫자는 복소수이거나 대상 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.|  
|[operator/=](#op_div_eq)|대상 복소수를 제수로 나눕니다. 제수는 복소수이거나 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.|  
|[operator=](#op_eq)|대상 복소수에 숫자를 할당합니다. 여기서 할당되는 숫자는 복소수이거나 대상 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: \<complex>  
  
 **네임스페이스:** std  
  
##  <a name="complex"></a>  complex::complex  
 지정된 실수 및 허수 부분을 사용하거나 다른 복소수의 복사본으로 복소수를 생성합니다.  
  
```  
constexpr complex(
    const T& 
    _RealVal = 0  ,   
    const T& 
    _ImagVal = 0);

    template <class Other>  
constexpr complex(
    const complex<Other>& 
    complexNum);
```  
  
### <a name="parameters"></a>매개 변수  
 `_RealVal`  
 생성되고 있는 복소수를 초기화하는데 사용되는 실수 부분의 값입니다.  
  
 `_ImagVal`  
 생성되고 있는 복소수를 초기화하는데 사용되는 허수 부분의 값입니다.  
  
 `complexNum`  
 해당 실수 및 허수 부분이 생성되고 있는 복소수를 초기화하는데 사용되는 복소수입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 생성자는 저장된 실수부를 _ *RealVal*로, 저장된 허수부를 \_ *Imagval*로 초기화합니다. 두 번째 생성자는 저장된 실수부를 `complexNum`**.real**()로, 저장된 허수부를 `complexNum`**.imag**()로 초기화합니다.  
  
 이 구현에서 변환기가 멤버 템플릿 함수를 지원하지 않는 경우는 결과는 다음과 같습니다.  
  
```  
template <class Other>  
complex(const complex<Other>& right);
```  
  
 위 템플릿이 아래 템플릿으로 바뀝니다.  
  
```  
 
complex(const complex& right);
```  
  
 위 템플릿은 복사 생성자입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_complex.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;   
  
   // The first constructor specifies real & imaginary parts  
   complex <double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,"  
        << "c1 = " << c1 << endl;   
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of another complex number  
   complex <double> c2 ( c1 );  
   cout << "Initializing with the real and imaginary parts of c1,"  
        << " c2 = " << c2 << endl;   
  
   // Complex numbers can be initialized in polar form  
   // but will be stored in Cartesian form  
   complex <double> c3 ( polar ( sqrt( (double)8 ) , pi / 4 ) );  
   cout << "c3 = polar ( sqrt ( 8 ) , pi / 4 ) = " << c3 << endl;   
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3 );  
   double argc3 = arg ( c3 );  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
```  
  
##  <a name="imag"></a>  complex::imag  
 복소수의 허수 구성 요소를 추출합니다.  
  
```  
T imag() const;

 
T imag(const T& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 허수 값을 추출할 복소수입니다.  
  
### <a name="return-value"></a>반환 값  
 복소수의 허수 부분입니다.  
  
### <a name="remarks"></a>설명  
 복소수 *a + bi*의 경우 허수부 또는 성분은 *Im(a + bi) = b.*입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_imag.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   complex <double> c1 ( 4.0 , 3.0 );  
   cout << "The complex number c1 = " << c1 << endl;  
  
   double dr1 = c1.real ( );  
   cout << "The real part of c1 is c1.real ( ) = "  
        << dr1 << "." << endl;  
  
   double di1 = c1.imag ( );  
   cout << "The imaginary part of c1 is c1.imag ( ) = "  
        << di1 << "." << endl;  
}  
```  
  
```Output  
The complex number c1 = (4,3)  
The real part of c1 is c1.real ( ) = 4.  
The imaginary part of c1 is c1.imag ( ) = 3.  
```  
  
##  <a name="op_star_eq"></a>  complex::operator*=  
 대상 복소수와 요소를 곱합니다. 요소는 복소수이거나 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.  
  
```  
template <class Other>  
complex& operator*=(const complex<Other>& right);

complex<Type>& operator*=(const Type& right);

complex<Type>& operator*=(const complex<Type>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 복소수 또는 대상 복소수의 매개 변수와 같은 형식의 숫자입니다.  
  
### <a name="return-value"></a>반환 값  
 매개 변수로 지정된 수와 곱한 복소수입니다.  
  
### <a name="remarks"></a>설명  
 연산이 오버로드되어 특정 형식으로 데이터를 변환하지 않고 단순한 산술 연산을 실행할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_op_me.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // Example of the first member function  
   // type complex<double> multiplied by type complex<double>  
   complex <double> cl1 ( polar ( 3.0 , pi / 6 ) );  
   complex <double> cr1 ( polar ( 2.0 , pi / 3 ) );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   complex <double> cs1 = cl1 * cr1;  
   cout << "Quotient of two complex numbers is: cs1 = cl1 * cr1 = "  
        << cs1 << endl;  
  
   // This is equivalent to the following operation  
   cl1 *= cr1;  
   cout << "Quotient of two complex numbers is also: cl1 *= cr1 = "  
        << cl1 << endl;  
  
   double abscl1 = abs ( cl1 );  
   double argcl1 = arg ( cl1 );  
   cout << "The modulus of cl1 is: " << abscl1 << endl;  
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "   
        << argcl1 * 180 / pi << " degrees." << endl << endl;   
  
   // Example of the second member function  
   // type complex<double> multiplied by type double  
   complex <double> cl2 ( polar ( 3.0 , pi / 6 ) );  
   double cr2 = 5.0;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   complex <double> cs2 = cl2 * cr2;  
   cout << "Quotient of two complex numbers is: cs2 = cl2 * cr2 = "   
        << cs2 << endl;  
  
   // This is equivalent to the following operation  
   cl2 *= cr2;  
   cout << "Quotient of two complex numbers is also: cl2 *= cr2 = "  
        << cl2 << endl;  
  
   double abscl2 = abs ( cl2 );  
   double argcl2 = arg ( cl2 );  
   cout << "The modulus of cl2 is: " << abscl2 << endl;  
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "   
        << argcl2 * 180 / pi << " degrees." << endl;  
}  
```  
  
##  <a name="op_add_eq"></a>  complex::operator+=  
 대상 복소수에 숫자를 더합니다. 여기서 더해지는 숫자는 복소수이거나 대상 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.  
  
```  
template <class Other>  
complex<Type>& operator+=(const complex<Other>& right);

complex<Type>& operator+=(const Type& right);

complex<Type>& operator+=(const complex<Type>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 복소수 또는 대상 복소수의 매개 변수와 같은 형식의 숫자입니다.  
  
### <a name="return-value"></a>반환 값  
 추가되는 매개 변수로 지정된 숫자를 포함하는 복소수입니다.  
  
### <a name="remarks"></a>설명  
 연산이 오버로드되어 특정 형식으로 데이터를 변환하지 않고 단순한 산술 연산을 실행할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_op_pe.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // Example of the first member function  
   // type complex<double> added to type complex<double>  
   complex <double> cl1 ( 3.0 , 4.0 );  
   complex <double> cr1 ( 2.0 , -1.0 );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   complex <double> cs1 = cl1 + cr1;  
   cout << "The sum of the two complex numbers is: cs1 = cl1 + cr1 = "  
        << cs1 << endl;  
  
   // This is equivalent to the following operation  
   cl1 += cr1;  
   cout << "The complex number cr1 added to the complex number cl1 is:"  
        << "\n cl1 += cr1 = " << cl1 << endl;  
  
   double abscl1 = abs ( cl1 );  
   double argcl1 = arg ( cl1 );  
   cout << "The modulus of cl1 is: " << abscl1 << endl;  
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "   
        << argcl1 * 180 / pi << " degrees." << endl << endl;   
  
   // Example of the second member function  
   // type double added to type complex<double>  
   complex <double> cl2 ( -2 , 4 );  
   double cr2 =5.0;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   complex <double> cs2 = cl2 + cr2;  
   cout << "The sum of the two complex numbers is: cs2 = cl2 + cr2 = "   
        << cs2 << endl;  
  
   // This is equivalent to the following operation  
   cl2 += cr2;  
   cout << "The complex number cr2 added to the complex number cl2 is:"  
        << "\n cl2 += cr2 = " << cl2 << endl;  
  
   double abscl2 = abs ( cl2 );  
   double argcl2 = arg ( cl2 );  
   cout << "The modulus of cl2 is: " << abscl2 << endl;  
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "   
        << argcl2 * 180 / pi << " degrees." << endl << endl;  
}  
```  
  
```Output  
The left-side complex number is cl1 = (3,4)  
The right-side complex number is cr1 = (2,-1)  
The sum of the two complex numbers is: cs1 = cl1 + cr1 = (5,3)  
The complex number cr1 added to the complex number cl1 is:  
 cl1 += cr1 = (5,3)  
The modulus of cl1 is: 5.83095  
The argument of cl1 is: 0.54042 radians, which is 30.9638 degrees.  
  
The left-side complex number is cl2 = (-2,4)  
The right-side complex number is cr2 = 5  
The sum of the two complex numbers is: cs2 = cl2 + cr2 = (3,4)  
The complex number cr2 added to the complex number cl2 is:  
 cl2 += cr2 = (3,4)  
The modulus of cl2 is: 5  
The argument of cl2 is: 0.927295 radians, which is 53.1301 degrees.  
```  
  
##  <a name="complex__operator-_eq"></a>  complex::operator-=  
 대상 복소수에서 숫자를 뺍니다. 여기서 빼는 숫자는 복소수이거나 대상 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.  
  
```  
template <class Other>  
complex<Type>& operator-=(const complex<Other>& complexNum);

complex<Type>& operator-=(const Type& _RealPart);

complex<Type>& operator-=(const complex<Type>& complexNum);
```  
  
### <a name="parameters"></a>매개 변수  
 `complexNum`  
 대상 복소수에서 뺄 복소수입니다.  
  
 `_RealPart`  
 대상 복소수에서 뺄 실수입니다.  
  
### <a name="return-value"></a>반환 값  
 뺄 매개 변수로 지정된 숫자를 포함하는 복소수입니다.  
  
### <a name="remarks"></a>설명  
 연산이 오버로드되어 특정 형식으로 데이터를 변환하지 않고 단순한 산술 연산을 실행할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_op_se.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // Example of the first member function  
   // type complex<double> subtracted from type complex<double>  
   complex <double> cl1 ( 3.0 , 4.0 );  
   complex <double> cr1 ( 2.0 , -1.0 );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   complex <double> cs1 = cl1 - cr1;  
   cout << "The difference between the two complex numbers is:"  
        << "\n cs1 = cl1 - cr1 = " << cs1 << endl;  
  
   // This is equivalent to the following operation  
   cl1 -= cr1;  
   cout << "Complex number cr1 subtracted from complex number cl1 is:"  
        << "\n cl1 -= cr1 = " << cl1 << endl;  
  
   double abscl1 = abs ( cl1 );  
   double argcl1 = arg ( cl1 );  
   cout << "The modulus of cl1 is: " << abscl1 << endl;  
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "   
        << argcl1 * 180 / pi << " degrees." << endl << endl;   
  
   // Example of the second member function  
   // type double subtracted from type complex<double>  
   complex <double> cl2 ( 2.0 , 4.0 );  
   double cr2 = 5.0;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   complex <double> cs2 = cl2 - cr2;  
   cout << "The difference between the two complex numbers is:"  
        << "\n cs2 = cl2 - cr2 = " << cs2 << endl;  
  
   // This is equivalent to the following operation  
   cl2  -= cr2;  
   cout << "Complex number cr2 subtracted from complex number cl2 is:"  
        << "\n cl2 -= cr2 = " << cl2 << endl;  
  
   double abscl2 = abs ( cl2 );  
   double argcl2 = arg ( cl2 );  
   cout << "The modulus of cl2 is: " << abscl2 << endl;  
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "   
        << argcl2 * 180 / pi << " degrees." << endl << endl;  
}  
```  
  
```Output  
The left-side complex number is cl1 = (3,4)  
The right-side complex number is cr1 = (2,-1)  
The difference between the two complex numbers is:  
 cs1 = cl1 - cr1 = (1,5)  
Complex number cr1 subtracted from complex number cl1 is:  
 cl1 -= cr1 = (1,5)  
The modulus of cl1 is: 5.09902  
The argument of cl1 is: 1.3734 radians, which is 78.6901 degrees.  
  
The left-side complex number is cl2 = (2,4)  
The right-side complex number is cr2 = 5  
The difference between the two complex numbers is:  
 cs2 = cl2 - cr2 = (-3,4)  
Complex number cr2 subtracted from complex number cl2 is:  
 cl2 -= cr2 = (-3,4)  
The modulus of cl2 is: 5  
The argument of cl2 is: 2.2143 radians, which is 126.87 degrees.  
```  
  
##  <a name="op_div_eq"></a>  complex::operator/=  
 대상 복소수를 제수로 나눕니다. 제수는 복소수이거나 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.  
  
```  
template <class Other>  
complex<Type>& operator/=(const complex<Other>& complexNum);

complex<Type>& operator/=(const Type& _RealPart);

complex<Type>& operator/=(const complex<Type>& complexNum);
```  
  
### <a name="parameters"></a>매개 변수  
 `complexNum`  
 대상 복소수에서 뺄 복소수입니다.  
  
 `_RealPart`  
 대상 복소수에서 뺄 실수입니다.  
  
### <a name="return-value"></a>반환 값  
 매개 변수로 지정된 숫자로 나눈 복소수입니다.  
  
### <a name="remarks"></a>설명  
 연산이 오버로드되어 특정 형식으로 데이터를 변환하지 않고 단순한 산술 연산을 실행할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_op_de.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // Example of the first member function  
   // type complex<double> divided by type complex<double>  
   complex <double> cl1 ( polar (3.0 , pi / 6 ) );  
   complex <double> cr1 ( polar (2.0 , pi / 3 ) );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   complex <double> cs1 = cl1 / cr1;  
   cout << "The quotient of the two complex numbers is: cs1 = cl1 /cr1 = "  
        << cs1 << endl;  
  
   // This is equivalent to the following operation  
   cl1 /= cr1;  
   cout << "Quotient of two complex numbers is also: cl1 /= cr1 = "  
        << cl1 << endl;  
  
   double abscl1 = abs ( cl1 );  
   double argcl1 = arg ( cl1 );  
   cout << "The modulus of cl1 is: " << abscl1 << endl;  
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "   
        << argcl1 * 180 / pi << " degrees." << endl << endl;   
  
   // Example of the second member function  
   // type complex<double> divided by type double  
   complex <double> cl2 ( polar (3.0 , pi / 6 ) );  
   double cr2 =5;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   complex <double> cs2 = cl2 / cr2;  
   cout << "The quotient of the two complex numbers is: cs2 /= cl2 cr2 = "   
        << cs2 << endl;  
  
   // This is equivalent to the following operation  
   cl2 /= cr2;  
   cout << "Quotient of two complex numbers is also: cl2 = /cr2 = "  
        << cl2 << endl;  
  
   double abscl2 = abs ( cl2 );  
   double argcl2 = arg ( cl2 );  
   cout << "The modulus of cl2 is: " << abscl2 << endl;  
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "   
        << argcl2 * 180 / pi << " degrees." << endl << endl;  
}  
```  
  
```Output  
The left-side complex number is cl1 = (2.59808,1.5)  
The right-side complex number is cr1 = (1,1.73205)  
The quotient of the two complex numbers is: cs1 = cl1 /cr1 = (1.29904,-0.75)  
Quotient of two complex numbers is also: cl1 /= cr1 = (1.29904,-0.75)  
The modulus of cl1 is: 1.5  
The argument of cl1 is: -0.523599 radians, which is -30 degrees.  
  
The left-side complex number is cl2 = (2.59808,1.5)  
The right-side complex number is cr2 = 5  
The quotient of the two complex numbers is: cs2 /= cl2 cr2 = (0.519615,0.3)  
Quotient of two complex numbers is also: cl2 = /cr2 = (0.519615,0.3)  
The modulus of cl2 is: 0.6  
The argument of cl2 is: 0.523599 radians, which is 30 degrees.  
```  
  
##  <a name="op_eq"></a>  complex::operator=  
 대상 복소수에 숫자를 할당합니다. 여기서 할당되는 숫자는 복소수이거나 대상 복소수의 실수부 및 허수부와 동일한 형식일 수 있습니다.  
  
```  
template <class Other>  
complex<Type>& operator=(const complex<Other>& right);

complex<Type>& operator=(const Type& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 복소수 또는 대상 복소수의 매개 변수와 같은 형식의 숫자입니다.  
  
### <a name="return-value"></a>반환 값  
 매개 변수로 지정된 숫자가 할당된 복소수입니다.  
  
### <a name="remarks"></a>설명  
 연산이 오버로드되어 특정 형식으로 데이터를 변환하지 않고 단순한 산술 연산을 실행할 수 있습니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_op_as.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // Example of the first member function  
   // type complex<double> assigned to type complex<double>  
   complex <double> cl1 ( 3.0 , 4.0 );  
   complex <double> cr1 ( 2.0 , -1.0 );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   cl1  = cr1;  
   cout << "The complex number cr1 assigned to the complex number cl1 is:"  
        << "\n cl1 = cr1 = " << cl1 << endl;  
  
   // Example of the second member function  
   // type double assigned to type complex<double>  
   complex <double> cl2 ( -2 , 4 );  
   double cr2 =5.0;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   cl2 = cr2;  
   cout << "The complex number cr2 assigned to the complex number cl2 is:"  
        << "\n cl2 = cr2 = " << cl2 << endl;  
  
   cl2 = complex<double>(3.0, 4.0);  
   cout << "The complex number (3, 4) assigned to the complex number cl2 is:"  
        << "\n cl2 = " << cl2 << endl;  
}  
```  
  
```Output  
The left-side complex number is cl1 = (3,4)  
The right-side complex number is cr1 = (2,-1)  
The complex number cr1 assigned to the complex number cl1 is:  
 cl1 = cr1 = (2,-1)  
The left-side complex number is cl2 = (-2,4)  
The right-side complex number is cr2 = 5  
The complex number cr2 assigned to the complex number cl2 is:  
 cl2 = cr2 = (5,0)  
The complex number (3, 4) assigned to the complex number cl2 is:  
 cl2 = (3,4)  
```  
  
##  <a name="real"></a>  complex::real  
 복소수의 실수 구성 요소를 가져오거나 설정합니다.  
  
```  
constexpr T real() const;

 
T real(const T& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 실수 값을 추출할 복소수입니다.  
  
### <a name="return-value"></a>반환 값  
 복소수의 실수 부분입니다.  
  
### <a name="remarks"></a>설명  
 복소수 *a + bi*의 경우 실수부 또는 성분은 *Re(a + bi) = a.*입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_class_real.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   complex <double> c1 ( 4.0 , 3.0 );  
   cout << "The complex number c1 = " << c1 << endl;  
  
   double dr1 = c1.real ( );  
   cout << "The real part of c1 is c1.real ( ) = "  
        << dr1 << "." << endl;  
  
   double di1 = c1.imag ( );  
   cout << "The imaginary part of c1 is c1.imag ( ) = "  
        << di1 << "." << endl;  
}  
```  
  
```Output  
The complex number c1 = (4,3)  
The real part of c1 is c1.real ( ) = 4.  
The imaginary part of c1 is c1.imag ( ) = 3.  
```  
  
##  <a name="value_type"></a>  complex::value_type  
 복소수의 실수부와 허수부를 나타내는 데 사용되는 데이터 형식을 표시하는 형식입니다.  
  
```  
 
typedef Type value_type;  
```  
  
### <a name="remarks"></a>설명  
 `value_type`은 complex 클래스 **Type** 템플릿 매개 변수의 동의어입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// complex_valuetype.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   complex <double>::value_type a = 3, b = 4;  
  
   complex <double> c1 ( a , b );  
   cout << "Specifying initial real & imaginary parts"  
      << "\nof type value_type: "  
      << "c1 = " << c1 << "." << endl;  
}  
```  
  
```Output  
Specifying initial real & imaginary parts  
of type value_type: c1 = (3,4).  
```  
  
## <a name="see-also"></a>참고 항목  
 [complex 멤버](http://msdn.microsoft.com/en-us/d5c4466c-43a0-4817-aca1-9a5d492dae28)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)


