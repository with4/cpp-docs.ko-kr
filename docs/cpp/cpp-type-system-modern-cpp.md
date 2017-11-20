---
title: "C + + 형식 시스템 (최신 c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 47d8fdec93c9d77e6648c5f648171a8ff349474d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-type-system-modern-c"></a>C++ 형식 시스템(최신 C++)
개념 *형식* c + +에서 매우 중요 합니다. 모든 변수, 함수 인수 및 함수 반환 값은 형식이 있어야 컴파일할 수 있습니다. 또한 모든 식(리터럴 값 포함)은 확인 전 컴파일러가 암시적으로 형식을 지정합니다. 형식의 몇 가지 예로 `int` 정수 계열 값을 저장 한 `double` 부동 소수점 값을 저장 한 (라고도 *스칼라* 데이터 형식), 또는 표준 라이브러리 클래스 [std::basic_string](../standard-library/basic-string-class.md) 텍스트를 저장 합니다. `class` 또는 `struct`를 정의하여 고유 형식을 만들 수 있습니다. 이 형식은 변수에 할당되는(또는 식 결과) 메모리 양, 해당 변수에 저장할 수 있는 값의 유형, 이러한 값(비트 패턴)의 해석 방법 및 여기에 대해 수행할 수 있는 작업을 지정합니다. 이 문서에는 C++ 형식 시스템의 주요 기능에 대한 비공식적 개요가 들어 있습니다.  
  
## <a name="terminology"></a>용어  
 **변수**: 상징적인 이름으로 데이터의 정의 된 코드 범위 전체에서 참조 데이터에 액세스 하는 이름을 사용할 수 있도록 합니다. C + +에서는 *변수* 다른 형식의 인스턴스는 일반적으로 라고 하는 반면 스칼라 데이터 형식의 인스턴스를 나타내는 데 일반적으로 사용 *개체*합니다.  
  
 **개체**: 단순 성과 일관성에 대 한이 문서에서는 용어 *개체* 참조 하는 클래스 또는 구조체의 및 일반적인 의미에서 사용 하는 경우 모든 인스턴스는 모든 형식을 포함 스칼라 변수입니다.  
  
 **POD 형식의** (일반 이전 데이터): c + +에는 데이터 형식 비공식적 범주는 스칼라 형식 가리킵니다 (기본 유형 섹션 참조) 또는 *POD 클래스*합니다. POD 클래스는 POD가 아닌 정적 데이터 멤버가 없으며 사용자 정의 생성자, 사용자 정의 소멸자 또는 사용자 정의 할당 연산자가 없습니다. 또한 POD 클래스에는 가상의 함수, 기본 클래스 및 비공개 또는 보호된 비정적 데이터 멤버가 없습니다. POD 유형은 주로 외부 데이터 교환(예: POD 유형만 있는 C 언어로 작성된 모듈)에 사용됩니다.  
  
## <a name="specifying-variable-and-function-types"></a>변수 및 함수 형식 지정  
 C + +는는 *강력한 형식의* 언어 이며 *정적 형식의*; 모든 개체에는 형식 및 형식 (하지 정적 데이터 개체와 혼동 해서는)을 변경 불가능 합니다.   
**변수를 선언 하는 경우** 코드에 해당 형식을 명시적으로 지정 하거나 사용 하 여는 `auto` 이니셜라이저에서 형식을 추론 하도록 컴파일러에 지시 하는 키워드입니다.   
**함수를 선언 하는 경우** 각 인수의 형식과 반환 값을 지정 해야 코드에서 또는 `void` 함수에서 반환 값이 없는 경우. 임의 형식의 인수를 허용하는 함수 템플릿을 사용하는 경우는 예외입니다.  
  
 먼저 변수를 선언한 후에는 나중에 형식을 변경할 수 없습니다. 그러나 변수 값 또는 함수의 반환 값을 다른 형식의 다른 변수에 복사할 수 있습니다. 이러한 연산을 라고 *형식 변환*, 있는 경우에 따라 필요 하지만 데이터가 손실 되거나 오류 발생할 수 있는 곳도 있습니다.  
  
 POD 형식의 변수를 선언할 때 초기화, 즉 초기 값을 제공하는 것이 좋습니다. 변수를 초기화할 때까지 해당 메모리 위치에 이전에 있던 비트로 구성된 "가비지" 값을 가지고 있습니다. 특히 초기화를 처리하는 다른 언어를 사용하는 경우 C++의 이 특성을 기억해야 합니다. 비 POD 클래스 형식의 변수를 선언할 경우 생성자가 초기화를 처리합니다.  
  
 다음 예제에서는 각각에 대한 일부 설명을 포함한 몇 가지 간단한 변수 선언을 보여 줍니다. 또한 컴파일러가 특정 변수의 후속 작업을 허용하거나 거부하기 위해 형식 정보를 사용하는 방법을 보여줍니다.  
  
```  
  
int result = 0;              // Declare and initialize an integer.  
double coefficient = 10.8;   // Declare and initialize a floating   
                             // point value.  
auto name = "Lady G.";       // Declare a variable and let compiler   
                             // deduce the type.  
auto address;                // error. Compiler cannot deduce a type   
                             // without an intializing value.  
age = 12;                    // error. Variable declaration must  
                             // specify a type or use auto!  
result = "Kenny G.";         // error. Can’t assign text to an int.  
string result = "zero";      // error. Can’t redefine a variable with  
                             // new type.  
int maxValue;                // Not recommended! maxValue contains   
                             // garbage bits until it is initialized.  
  
```  
  
## <a name="fundamental-built-in-types"></a>기본(기본 제공) 형식  
 일부 언어와 달리, C++에는 다른 형식이 파생되는 유니버설 기본 형식이 없습니다. 언어의 Visual c + + 구현에는 많은 *기본 형식을*라고도 *기본 제공 형식*합니다. 여기에는 `int`, `double`, `long`, `bool`과 `char` 및 `wchar_t` 형식(각각 ASCII 및 UNICODE 문자용)과 같은 숫자 형식이 포함됩니다. 가장 기본적인 유형(`bool`,`double`, `wchar_t`와 관련 유형 제외)에는 변수가 저장할 수 있는 값의 범위를 수정해주는 미등록 버전이 있습니다. 예를 들어 32비트 부호 있는 정수를 저장하는 `int`는 -2,147,483,648에서 2,147,483,647 사이의 값을 나타낼 수 있습니다. 또한 32비트로 저장되는 `unsigned int`는 0에서 4,294,967,295 사이의 값을 저장할 수 있습니다. 각 사례에서 사용할 수 있는 값의 총 수는 동일하며, 범위만 다릅니다.  
  
 제어 기본 항목은 어떤 작업을 수행할 수 있는지 및 기본 형식 및 방법들이 다른 기본 형식으로 변환될 수 있는지를 통제하도록 만든 컴파일러에 의해 인식됩니다. 기본 제공 형식 및 크기와 숫자 제한의 전체 목록은 참조 하십시오. [기본 형식을](../cpp/fundamental-types-cpp.md)합니다.  
  
 다음 그림은 기본 제공 형식의 상대적 크기를 보여 줍니다.  
  
 ![크기를 바이트로 작성 &#45; 형식에](../cpp/media/built-intypesizes.png "내장 inTYpeSizes")  
  
 다음 표에는 가장 자주 사용하는 기본 형식이 나와 있습니다.  
  
|형식|크기|주석|  
|----------|----------|-------------|  
|int|4바이트|정수 값에 대한 기본 선택입니다.|  
|double|8바이트|부동 소수점 값에 대한 기본 선택입니다.|  
|bool|1바이트|true 또는 false가 될 수 있는 값을 나타냅니다.|  
|char|1바이트|UNICODE로 변환되지 않는 이전 C 스타일 문자열 또는 std::string 개체의 ASCII 문자에 사용합니다.|  
|wchar_t|2바이트|UNICODE 형식(Windows의 경우 UTF-16, 운영 체제마다 다를 수 있음)으로 인코딩할 수 있는 "와이드" 문자 값을 나타냅니다. `std::wstring` 형식 문자열에 사용되는 문자 형식입니다.|  
|unsigned char|1바이트|C++에는 기본 `byte` 형식이 없습니다.  바이트 값을 나타내려면 부호 없는 문자를 사용합니다.|  
|unsigned int|4바이트|비트 플래그에 대한 기본 선택입니다.|  
|long long|8바이트|매우 큰 정수 값을 나타냅니다.|  
  
## <a name="the-void-type"></a>void 형식입니다.  
 `void` 형식은 특수한 형식입니다. `void` 형식의 변수는 선언할 수 없지만 원시(형식화되지 않은) 메모리를 할당할 때 필요한 `void *`(`void` 포인터) 형식의 변수는 선언할 수 있습니다. 그러나 `void`에 대한 포인터는 형식이 안전하지 않으며 일반적으로 최신 C++에서 사용하지 않는 것이 좋습니다. 함수 선언에서 `void` 반환 값은 해당 함수가 값을 반환하지 않음을 의미합니다. 이는 일반적이고 허용 가능한 `void` 사용 방식입니다. C 언어는 매개 변수 목록에서 `void`를 선언하는 0 매개 변수를 가진 함수가 필요했지만(예: `fou(void)`), 최신 C++에서는 이 방식을 사용하지 않고 `fou()`를 선언해야 합니다. 자세한 내용은 참조 [형식 변환 및 형식 안전성](../cpp/type-conversions-and-type-safety-modern-cpp.md)합니다.  
  
## <a name="const-type-qualifier"></a>const 형식 한정자  
 기본 제공 또는 사용자 정의 형식은 const 키워드로 정규화할 수 있습니다. 또한 멤버 함수는 `const` 한정 또는 `const` 오버로드일 수 있습니다. `const` 형식 값은 초기화한 후 수정할 수 없습니다.  
  
```  
  
const double PI = 3.1415;  
PI = .75 //Error. Cannot modify const variable.  
  
```  
  
 `const` 한정자는 함수 및 변수 선언에 광범위하게 사용되며 "const 정확성"은 C++의 중요한 개념입니다. 기본적으로 `const`를 사용하는 것은 컴파일 타임에 값이 실수로 수정되지 않는 것을 보장합니다. 자세한 내용은 참조 [const](../cpp/const-cpp.md)합니다.  
  
 `const` 형식은 비const 버전과 구분됩니다. 예를 들어, `const int`는 `int`와 구분되는 형식입니다. C + +를 사용할 수 있습니다 `const_cast` 제거 해야 하는 드문 경우 이지만 연산자 *const 특성* 변수에서 합니다. 자세한 내용은 참조 [형식 변환 및 형식 안전성](../cpp/type-conversions-and-type-safety-modern-cpp.md)합니다.  
  
## <a name="string-types"></a>String 형식  
 엄격히 말해서, c + + 언어는 기본 제공 문자열 형식이 없습니다. `char` 및 `wchar_t` 단일 문자를 저장-종결 null 값을 추가 하는 문자열 근사치를 구하려면 이러한 형식의 배열이 선언 해야 합니다 (예를 들어, ASCII `'\0'`) 마지막 문자를 지난 유효한 배열 요소 하나 (라고도 *C 스타일 문자열*). 훨씬 더 많은 코드를 작성해야 하거나 외부 문자열 유틸리티 라이브러리 함수를 사용해야 하는 C 스타일 문자열입니다. 그러나 현대적인 C++에는 표준 라이브러리 형식 `std::string`(8비트 `char`-type 문자열일 경우) 또는 `std::wstring`(16비트 `wchar_t`-type 문자열일 경우)이 있습니다. 모든 호환 c + + 빌드 환경에 포함 된 표준 라이브러리의 일부 이므로 이러한 c + + 표준 라이브러리 컨테이너 네이티브 문자열 형식으로 생각할 수 있습니다. 간단히 `#include <string>` 지시문을 사용하여 이러한 형식을 프로그램에서 사용할 수 있도록 만듭니다. (MFC 또는 ATL을 사용하지 않는 경우 CString 클래스도 사용할 수 있지만 C++ 표준에 포함되지는 않습니다.) 현대 C++에서는 null로 끝나는 문자 배열(앞에서 언급한 C 스타일 문자열)을 사용하지 않는 것이 좋습니다.  
  
## <a name="user-defined-types"></a>사용자 정의 형식  
 `class`, `struct`, `union` 또는 `enum`을 정의하면 해당 구문이 기본 형식인 것처럼 코드의 나머지에 사용됩니다. 메모리 크기는 잘 알려져 있고, 사용법에 관한 규정이 컴파일 타임 검사, 가동 시 프로그램 수명 점검을 위해 적용됩니다. 기본 제공 형식과 사용자 정의 형식 간 기본적 차이는 다음과 같습니다.  
  
-   컴파일러는 기본적으로 사용자 정의 형식을 인식하지 못합니다. 컴파일 프로세스 중 정의 처음으로 발견할 때 형식의 알아냅니다.  
  
-   오버로드를 통해 적합한 연산자를 클래스 멤버 또는 비멤버 함수로 정의하여 해당 형식에서 수행할 수 있는 연산자와 다른 형식으로 변환할 수 있는 방법을 지정합니다. 자세한 내용은 참조 [함수 오버 로드](function-overloading.md)합니다.  
  
-   정적 형식(개체 형식을 절대 변경할 수 없는 규칙)일 필요는 없습니다. 메커니즘을 통해 *상속* 및 *다형성*, 클래스 (클래스의 개체 인스턴스라고 부름)의 사용자 정의 유형으로 선언 된 변수가 런타임에 보다에서 다른 형식을 가질 수 있습니다 컴파일 시간입니다. 자세한 내용은 [상속](../cpp/inheritance-cpp.md)을 참조하세요.  
  
## <a name="pointer-types"></a>포인터 형식  
 C 언어의 초기 버전부터 시작해서 C++에서는 계속하여 특수 선언자`*`(별표)를 사용하여 포인터 형식의 변수를 선언할 수 있습니다. 포인터 형식은 메모리에서 실제 데이터 값이 저장되는 위치의 주소를 저장합니다. 최신 c + +에서 이러한 라고 *원시 포인터*, 특수 연산자를 통해 코드에서 액세스 하 고 `*` (별표) 또는 `->` (있는 대시 큰-보다). 이 라고 *역참조*, 어떤 단추가 사용 하는 스칼라에 대 한 포인터 또는 멤버 개체에 대 한 포인터를 역참조는 여부에 따라 달라 집니다. 포인터 형식 사용은 C 및 C++ 프로그램 개발 환경에서 가장 까다롭고 복잡한 요소 중 하나였습니다. 이 섹션에서는 몇 가지 팩트 및 방법 하지만, 현대적인 c + + 것이 더 이상 필수 (또는 권장) 하려는 경우에 원시 포인터를 사용 하 여 설명의 진화 인해 전혀 개체 소유권에 대 한 원시 포인터를 사용 하는 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md) 드 ( 자세히 설명이 섹션의 끝). 원본 포인터를 개체 관찰 시 사용하면 편하고 안전하지만 개체 소유권 획득에 사용해야 할 경우 소유한 개체의 생성 및 제거 방법을 신중하게 고려하고 주의해서 사용해야 합니다.  
  
 가장 먼저 알아야 할 점은 원시 포인터 변수를 선언하는 것은 포인터 변수 역참조가 있는 경우 포인터를 참조하는 메모리 위치의 주소를 저장하는 데 필요한 메모리를 할당한다는 것입니다. 데이터 값 자체에 대 한 메모리의 할당 (호출 또한 *백업 저장소*) 아직 할당 되지 않습니다. 즉, 기본 포인터 변수를 선언하면 실제 데이터 변수가 아니라 메모리 주소 변수를 만듭니다. 포인터 변수에 백업 저장소에 대한 올바른 주소가 포함되어 있는지 확인하기 전에 포인터 변수를 역참조하면 프로그램에서 정의되지 않은 동작(일반적으로 심각한 오류)이 발생합니다. 다음 예제에서는 이런 종류의 오류를 보여 줍니다.  
  
```  
  
int* pNumber;       // Declare a pointer-to-int variable.  
*pNumber = 10;      // error. Although this may compile, it is  
                    // a serious error. We are dereferencing an  
                    // uninitialized pointer variable with no  
                    // allocated memory to point to.  
  
```  
  
 이 예제는 실제 정수 데이터 또는 할당된 유효한 메모리 주소를 저장하기 위해 할당된 메모리 없이 포인터를 역참조합니다. 다음은 다음 오류를 해결한 코드입니다.  
  
```  
  
    int number = 10;          // Declare and initialize a local integer  
                              // variable for data backing store.  
    int* pNumber = &number;   // Declare and initialize a local integer  
                              // pointer variable to a valid memory  
                              // address to that backing store.  
...  
    *pNumber = 41;            // Dereference and store a new value in   
                              // the memory pointed to by  
                              // pNumber, the integer variable called  
                              // "number". Note "number" was changed, not  
                              // "pNumber".  
  
```  
  
 수정된 코드 예제는 로컬 스택 메모리를 사용하여 `pNumber`가 가리키는 백업 저장소를 만듭니다. 간단히 기본 형식을 사용합니다. 포인터에 대 한 백업 저장소는 라는 메모리 영역에 동적으로 할당 되는 대부분 자주 사용자 정의 형식 실제로 *힙* (또는 *가능 저장소*)를 사용 하 여 한 `new` 키워드 식 (C 스타일 프로그래밍에서 이전 `malloc()` C 런타임 라이브러리 함수를 사용한). 할당 된 후 이러한 변수는 일반적으로 라고 개체 클래스 정의에 기반 하는 경우에 특히 합니다. `new`에 할당된 메모리는 해당`delete` 문에 의해 삭제되어야 합니다(또는 할당에 필요한 `malloc()` 기능인 C 런타임 기능 `free()`을 사용할 경우).  
  
 그러나 되기은 동적으로 할당 된 개체-특히 복잡 한 코드를 호출 하는 리소스 버그가에서 삭제를 잊기 쉬울는 *메모리 누수*합니다. 그러므로 최신 C++에서는 원시 포인터를 사용하지 않는 것이 좋습니다. 거의 항상 하는 것에 대 한 원시 포인터를 래핑하는 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md), (스마트 포인터에 대 한 범위에서 벗어날) 하는 경우 해당 소멸자가 호출 됩니다; 자동으로 메모리를 해제할 것는 스마트 포인터를 사용 하 여 있습니다 거의 c + + 프로그램에서 버그가 있는 모든 급을 제거 합니다. 다음 예에서 `MyClass`는 `DoSomeWork();`의 공용 메서드를 가진 사용자 정의 형식입니다.  
  
```  
  
void someFunction() {  
    unique_ptr<MyClass> pMc(new MyClass);  
    pMc->DoSomeWork();  
}  
  // No memory leak. Out-of-scope automatically calls the destructor  
  // for the unique_ptr, freeing the resource.  
  
```  
  
 스마트 포인터에 대 한 자세한 내용은 참조 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md)합니다.  
  
 포인터 변환에 대 한 자세한 내용은 참조 [형식 변환 및 형식 안전성](../cpp/type-conversions-and-type-safety-modern-cpp.md)합니다.  
  
 포인터에 대 한 자세한 내용은 참조 일반적으로 [포인터](../cpp/pointers-cpp.md)합니다.  
  
## <a name="windows-data-types"></a>Windows 데이터 형식  
 C 및 C++의 클래식 Win32 프로그래밍에서 대부분의 함수에는 매개 변수 및 반환 값 형식을 지정하는 Windows 관련 typedefs 및 #define 매크로(`windef.h`에 정의됨)가 사용됩니다. 이러한 Windows 데이터 유형은 대부분 C/c + + 기본 제공 형식에 지정 된 특수 이름 (별칭)입니다. 이러한 형식 정 및 전처리기 정의의 전체 목록은 참조 하십시오. [Windows 데이터 형식](http://msdn.microsoft.com/en-us/4553cafc-450e-4493-a4d4-cb6e2f274d46)합니다. HRESULT, LCID와 같은 이러한 typedefs 중 일부는 유용하며 설명을 포함합니다. INT와 같은 다른 형식은 특별한 의미가 없으며 기본적 C++ 형식의 별칭입니다. 그 외 Windows 데이터 유형은 C 프로그래밍 및 16비트 프로세서 시기부터 내려온 이름을 그대로 가지고 있으며 최신 하드웨어 또는 운영 체제에 다른 목적과 의미를 가지고 있지 않습니다. 특수 데이터 형식으로 나열 된 Windows 런타임 라이브러리와 연결 된 사항도 [Windows 런타임 기본 데이터 형식을](http://msdn.microsoft.com/en-us/b5735851-ec07-48c1-92b4-ca9f768096f6)합니다. 현대적인 C++에서 일반적인 지침은 Windows 형식이 값 해석 방식에 대해 추가적인 의미를 전달하지 않는 한 C++ 기본 형식을 사용하는 것입니다.  
  
## <a name="more-information"></a>추가 정보  
 C++ 형식 시스템에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
|||  
|-|-|  
|[값 형식](../cpp/value-types-modern-cpp.md)|설명 *값 형식이* 용도 관련 된 문제와 함께 합니다.|  
|[형식 변환 및 형식 안전성](../cpp/type-conversions-and-type-safety-modern-cpp.md)|일반적인 형식 변환 문제를 설명하고 이러한 문제를 방지하는 방법을 보여 줍니다.|  
  
## <a name="see-also"></a>참고 항목  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)