---
title: "형식 변환 및 형식 안전성(최신 C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 629b361a-2ce1-4700-8b5d-ab4f57b245d5
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 형식 변환 및 형식 안전성(최신 C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서 형식은 변환 관련 일반적인 문제를 식별하고 C\+\+ 코드에서 이 것을 방지 하는 방법에 대해 설명합니다.  
  
 C\+\+ 프로그램을 작성 하는 경우 형식 안전성이 확인되어야 합니다.  즉 모든 변수, 함수 인수 및 함수 반환 값에 적합한 종류의 데이터를 저장하고 다른 형식의 값을 포함하는 작업이 "합리적"이며 잘못 해석된 데이터 손실이 발생하지 않고 비트 패턴이 나 메모리 손상이 발생하지 않음을 의미합니다.  명시적으로 또는 암시적으로 값을 변환하지 않는 프로그램은 정의에 따라 형식 안전성이라고 정의합니다.  그러나 안전 하지 않은 변환에도 형식 변환이 필요한 경우가 있습니다.  예를 들어 `int` 형식의 변수에서 부동 소수점 작업의 결과를 저장해야 하는 경우가 있고 부호 없는 `int` 을 부호를 사용 하는 `int`를 가지는 함수에 전달 해야할 수도 있습니다.  두 예제는 데이터 손실 또는 값을 다시 해석 발생할 수 있기 때문에 안전하지 않은 변환을 설명합니다.  
  
 컴파일러에서 안전하지 않은 변환을 발견하면 오류 또는 경고를 알려줍니다.  오류가 컴파일을 중지합니다; 경고는 컴파일을 계속하게 할 수 있지만 코드에서 가능한 오류를 나타냅니다.  그러나 프로그램이 경고 없이 컴파일 될 경우라도 암시적 형식 변환을 이끄는 잘못 된 결과 생성 하는 코드를 가진 코드를 포함합니다.  코드에서 형식 오류는 코드에서 명시적 변환 또는 캐스트에서 나타날 수도 있습니다.  
  
## 암시적 형식 변환  
 기본 제공 없는 명시적 캐스트를 사용할 수 있는 여러 기본 제공 형식의 피연산자가 식에 피연산자 중 하나가 형식이 일치 하도록 변환할 때 컴파일러에서 빌트 인 *표준 변환* 을 사용하여 operands 중에 하나를 변환하여 타입이 매치가 되도록 합니다.  컴파일러는 하나가 성공할 때까지 잘 정의된 일련의 변환을 시도합니다.  만약 선택한 변환이 프로모션 인 경우 컴파일러 경고가 발생 하지 않습니다.  축소 변환인 경우 컴파일러가 데이터 손실에 대한 경고를 알려줍니다.  실제 데이터 손실이 발생 하는지 여부는 관련된 실제 값에 따라 다릅니다 하지만 이 경고를 오류로 처리 하는 것이 좋습니다.  사용자 정의 형식이 포함된 경우 컴파일러는 클래스 정의에 지정된 변환을 사용하여 시도합니다.  허용되는 변환, 찾을 수 없는 경우 컴파일러는 오류를 선언하고 프로그램이 컴파일되지 않습니다.  표준 변환을 제어하는 규칙에 대한 자세한 내용은 [표준 변환](../cpp/standard-conversions.md)를 참조하세요.  사용자 정의 변환에 대한 자세한 내용은 [사용자 정의 변환](../dotnet/user-defined-conversions-cpp-cli.md)을 참조하십시오.  
  
### 확대 변환 \(프로 모션\)  
 확대 변환에서 작은 변수에 대한 값은 데이터의 손실 없이 큰 변수에 할당됩니다.  안전 확대 변환은 항상 안전하므로 컴파일러는 자동으로 수행하고 경고를 선언하지 않습니다.  다음과 같은 변환은 확장 변환입니다.  
  
|전|후|  
|-------|-------|  
|부호 있는 또는 부호 없는 정수 계열 형식이 `long long` 또 `__int64`을 제외하고|`double`|  
|`bool` 또는 `char`|다른 빌드 인 형식|  
|`short` 또는 `wchar_t`|`int`, `long`, `long long`|  
|`int`, `long`|`long long`|  
|`float`|`double`|  
  
### 축소 변환 \(강제 변환\)  
 컴파일러에서 암시적 축소 변환을 수행하지만 잠재적인 데이터 손실에 대한 경고가 나타납니다.  이러한 경고를 매우 심각하게 받아드리세요.  만약 큰 변수에서 값이 작은 변수에 항상 들어갈 수 있기 때문에 데이터가 손실 되지 않을 것이라고 가정한다면 특정 경우 컴파일러에서 경고가 발생 하지 않도록 명시적 캐스트를 추가 합니다.  변환이 안전한지 확실하지 않은 경우 데이터 손실을 다루기 위해 코드에 런타임 검사 프로그램을 추가해서 잘못된 결과를 생성 하지 않도록 합니다.  이 시나리오를 처리하는 방법에 대해 다음을 [\(NOTINBUILD\)How to: Handle Narrowing Conversions \(C\+\+\)](http://msdn.microsoft.com/ko-kr/e483237e-501e-4a12-ac24-51526f6ddeaa)참조하십시오..  
  
 부동 소수점 형식에서 정수 계열 형식으로의 모든 변환은 소수점 값의 부분적 위치가 삭제되고 손실되기 때문에 축소 변환입니다.  
  
 다음 코드 예제에서는 일부 암시적 축소 변환 및 컴파일러가 실행하는 동안의 경고가 표시됩니다.  
  
```cpp  
  
int i = INT_MAX + 1; //warning C4307:'+':integral constant overflow  
wchar_t wch = 'A'; //OK  
char c = wch; // warning C4244:'initializing':conversion from 'wchar_t'  
              // to 'char', possible loss of data  
unsigned char c2 = 0xfffe; //warning C4305:'initializing':truncation from  
                           // 'int' to 'unsigned char'  
int j = 1.9f; // warning C4244:'initializing':conversion from 'float' to  
              // 'int', possible loss of data  
int k = 7.7; // warning C4244:'initializing':conversion from 'double' to  
             // 'int', possible loss of data  
  
```  
  
### 서명\-서명 되지 않은 변환  
 부호 있는 정수 형식 및 이에 상응 하는 부호는 항상 같은 크기이지만 값 변환에 대한 비트 패턴을 해석하는 방법에서는 서로 다릅니다.  다음 코드 예제에서는 부호 있는 값과 부호 없는 값으로 동일한 비트 패턴을 해석하는 경우를 보여줍니다.  `num` 및 `num2` 에 저장된 비트 패턴은 이전 그림에 표시되는 내용에 변경이 표시되지 않습니다.  
  
```cpp  
  
using namespace std;  
unsigned short num = numeric_limits<unsigned short>::max(); // #include <limits>  
short num2 = num;  
cout << "unsigned val = " << num << " signed val = " << num2 << endl;  
// Prints: unsigned val = 65535 signed val = -1  
  
// Go the other way.  
num2 = -1;  
num = num2;  
cout << "unsigned val = " << num << " signed val = " << num2 << endl;  
// Prints: unsigned val = 65535 signed val = -1  
  
```  
  
 값이 두 방향으로 다시 해석된다는 것을 확인하세요.  프로그램 결과가 원하는 것과 반전되는 홀수 값의 기호처럼 보이는 경우 서명되고 부호 없는 정수 계열 형식 사이의 암시적 변환을 찾습니다.  다음 예제에서는 `num`으로 저장 되었을 때 \(0\-1\)식의 결과가 `int` 에서 `unsigned int` 으로 암시적으로 변환 됩니다 .  이 것은 비트 패턴을 다시 해석하게 합니다.  
  
```cpp  
  
unsigned int u3 = 0 - 1;  
cout << u3 << endl; // prints 4294967295  
  
```  
  
 부호 있는 정수와 부호 없는 정수 계열 형식 간의 암시적 변환에 대해 컴파일러는 경고하지 않습니다.  따라서 서명에서 무서명으로의 변환을 완전히 방지하는 것이 좋습니다.  그 것을 피할수 없는 경우 변환 되는 값이 0 보다 크거나 같은지 또는 작거나 서명 유형의 최대 값과 같은지 확인하기 위해 코드에 런타임 검사를 추가합니다.  이 범위의 값은 다시 해석되지 않고 서명된 부호에서 서명되지 않은 부호로 또는 그와 반대로 전송됩니다.  
  
### 포인터 변환  
 많은 식에 C 스타일 배열은 포인터에서 배열의 첫 번째 요소에 대한 포인터로 암시적으로 변환되고 일정한 변환이 자동으로 발생할 수 있습니다.  이 방법은 편리 하지만 오류 발생 가능성이 있기도 합니다.  예를 들어 다음 잘못된 코드 예제가 터무니 없어보이더라도 Visual C\+\+을 컴파일하고 'p'의 결과를 도출합니다.  첫째 "도움말" 문자열 상수 리터럴은 배열의 첫째 요소를 가리키는 `char*` 로 변환되고; 다음은 포인터가 세 가지 요소에 의해 증가해서 마지막 요소 'p' 를 가리킵니다.  
  
```cpp  
  
char* s = "Help" + 3;  
  
```  
  
## 명시적 변환\(casts\)  
 캐스트 작업을 사용하여 특정 형식의 값을 다른 형식으로 변환하여 컴파일러에 지시할 수 있습니다.  컴파일러가 어떤 경우에 있어서 에러를 내보낼 것이지만 두 종류가 전혀 관계 없지만 어떤 경우에 있어서 작업이 형식\-안전이 아닐지라도 에러를 내보내진 않을 것입니다.  한 형식에서 다른 잠재적 변환은 프로그램 오류의 잠재적 원인이기 때문에 꼭 캐스트를 사용 합니다.  그러나 캐스트는 필요한 경우가 있으며 모든 캐스트가 동일하게 위험하진 않습니다.  캐스트의 효과적인 사용은 코드가 축소 변환을 수행하고 변환 프로그램이 잘못된 결과 생성을 유발하지 않는지 알고 있는 때입니다.  사실 이것은 컴파일러가 어떻게 할 것인지를 알 수 있게 하고 그 것으로 인한 경고로 함께 귀찮게 하지 않습니다.  또다른 사용은 포인터 파생 클래스에서 포인터 기본 클래스로 캐스팅하는 것입니다.  다른 사용은 변수의 대한 `const` 를 비\-`const` 인수를 필요로 하는 함수에 전달하기 위한 캐스입니다.  대부분의 이러한 캐스팅 작업은 일부 위험 작업을 포함합니다.  
  
 C 스타일의 프로그래밍에서는 같은 C 스타일 캐스트 연산자가 모든 종류의 캐스트에 사용됩니다.  
  
```cpp  
  
(int) x; // old-style cast, old-style syntax  
int(x); // old-style cast, functional syntax  
  
```  
  
 C 스타일 캐스트 연산자는 호출 연산자 \(\)와 동일하므로 간과하기 쉽고 코드에 눈에 띄지 않습니다.  둘 다 눈이나 검색으로 인식하기도 어렵습니다 그리고 그 들의 조합이 다음과 같기에 `static`, `const`, 및 `reinterpret_cast` 어렵습니다.  이전 스타일의 캐스트가 실제로 하는 것을 파악하는 것은 어렵고 오류가 발생할 수 있습니다.  이러한 모든 이유로 캐스팅이 필요할 때 어떤 경우에는 훨씬 더 형식\-안전하며 명시적으로 훨씬 프로그래밍 의도를 표현하는 다음 C\+\+ 캐스트 연산자를 사용할 것을 추천합니다.  
  
-   `static_cast`, 컴파일 시간만 확인 된 캐스트에 대하여.  만약 컴파일러가 완전히 호환 되지 않는 형식 간에 캐스팅을 발견한다면`static_cast` 는 에러를 반환합니다.  포인터에서 기본 및 포인터에서 파생으로 캐스팅에 사용할 수 있지만 컴파일러 변환이 런타임에 항상 안전할 것인지 확인할 수 없습니다.  
  
    ```cpp  
  
    double d = 1.58947;  
    int i = d;  // warning C4244 possible loss of data  
    int j = static_cast<int>(d);       // No warning.  
    string s = static_cast<string>(d); // Error C2440:cannot convert from  
                                       // double to std:string  
  
    // No error but not necessarily safe.  
    Base* b = new Base();  
    Derived* d2 = static_cast<Derived*>(b);  
  
    ```  
  
     자세한 내용은 [정적 캐스트](../cpp/static-cast-operator.md)를 참조하십시오.  
  
-   `dynamic_cast`, 안전하고 런타임 검사된 포인터에서 기본, 포인터에서 파생된 캐스트에 대하여  `dynamic_cast` 는 downcast에 대한 `static_cast` 보다 안전하지만 런타임 검사는 일부 오버 헤드를 초래합니다.  
  
    ```cpp  
  
    Base* b = new Base();  
  
    // Run-time check to determine whether b is actually a Derived*  
    Derived* d3 = dynamic_cast<Derived*>(b);  
  
    // If b was originally a Derived*, then d3 is a valid pointer.  
    if(d3)  
    {  
       // Safe to call Derived method.  
       cout << d3->DoSomethingMore() << endl;  
    }  
    else  
    {  
       // Run-time check failed.  
       cout << "d3 is null" << endl;  
    }  
  
    //Output: d3 is null;  
  
    ```  
  
     자세한 내용은 [dynamic\_cast](../cpp/dynamic-cast-operator.md)를 확인하세요.  
  
-   `const_cast`, 변수에 대한 `const`를 캐스팅하거나 비\-`const` 변수를 `const`로 변환하는 것.  이 연산자를 사용하여 `const`를 캐스팅하는 것은 C 스타일의 캐스팅을 사용하는 것과 같이 오류가 발생하기 쉽고 `const-cast` 를 제외하고 사용하는 것은 우연한 캐스팅을 수행할 가능성이 줄어듭니다.  어떤 경우 변수에 대한 `const`를 캐스트 할때도 있습니다. 예를 들어 전달하는 기능이 있는 `const` 변수를 비`const` 매개 변수를 갖는 함수로 변환하는 것입니다.  다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
    ```cpp  
  
    void Func(double& d) { ... }  
    void ConstCast()  
    {  
       const double pi = 3.14;  
       Func(const_cast<double&>(pi)); //No error.  
    }  
  
    ```  
  
     자세한 내용은 [const\_cast](../cpp/const-cast-operator.md)를 참조하십시오.  
  
-   `reinterpret_cast`, `pointer` 에서 `int`로 하는 관련 없는 형식들과의 케스트에 대하여.  
  
    > [!NOTE]
    >  이 캐스트 연산자는 일반적으로 다른 것들처럼 자주 사용되지 않고 다른 컴파일러로 컴파일 되는 것이 보증되지 않았습니다.  
  
     다음 예제에서는 어떻게 `reinterpret_cast` 가 `static_cast`로부터 다른지 보여줍니다.  
  
    ```cpp  
  
    const char* str = "hello";  
    int i = static_cast<int>(str);//error C2440: 'static_cast' : cannot  
                                  // convert from 'const char *' to 'int'  
    int j = (int)str; // C-style cast. Did the programmer really intend  
                      // to do this?  
    int k = reinterpret_cast<int>(str);// Programming intent is clear.  
                                       // However, it is not 64-bit safe.  
  
    ```  
  
     자세한 내용은 [reinterpret\_cast 연산자](../cpp/reinterpret-cast-operator.md)을 참조하십시오.  
  
## 참고 항목  
 [C\+\+ 형식 시스템](../cpp/cpp-type-system-modern-cpp.md)   
 [C\+\+의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)