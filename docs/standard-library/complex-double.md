---
title: complex&lt;double&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- complex/std::complex<double>
dev_langs:
- C++
helpviewer_keywords:
- complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d442e6b62a7e18a3b6025633ae5f12dde7915f3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844727"
---
# <a name="complexltdoublegt"></a>complex&lt;double&gt;

형식의 개체의 정렬된 된 쌍을 저장 하는 개체에 설명 **double ** 는 먼저 복소수와 두 번째 실수 부분을 나타내는 허수 부분을 나타내는입니다.

## <a name="syntax"></a>구문

```cpp
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

### <a name="parameters"></a>매개 변수

`RealVal` 형식의 값 **double** 생성 되 고 복소수의 실수 부분에 대 한 합니다.

`ImagVal` 형식의 값 **double** 생성 되 고 복소수의 허수 부분에 대 한 합니다.

`complexNum` 형식의 복소수입니다 **float** 또는 형식의 `long double` 실수 및 허수 부분으로 이루어진 형식의 복소수를 초기화할 때 사용 되 **double** 생성 되 고 있습니다.

## <a name="return-value"></a>반환 값

**double** 형식의 복소수입니다.

## <a name="remarks"></a>설명

**double** 형식의 complex 클래스에 대한 템플릿 클래스 complex의 명시적 특수화는 해당 특수화가 정의하는 생성자에서만 템플릿 클래스와 다릅니다. **float**에서 **double**로의 변환은 암시적일 수 있지만 `long double`에서 **double**로의 변환은 **명시적**이어야 합니다. **명시적**의 사용은 할당 구문을 사용하는 형식 변환의 시작을 배제합니다.

템플릿 클래스 `complex`에 대한 자세한 내용은 [complex 클래스](../standard-library/complex-class.md)를 참조하세요. 템플릿 클래스 `complex`의 멤버 목록은 다음을 참조하세요.

## <a name="example"></a>예제

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

## <a name="see-also"></a>참고자료

[complex 클래스](../standard-library/complex-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
