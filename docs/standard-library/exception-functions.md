---
title: '&lt;exception&gt; 함수 | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- exception/std::current_exception
- exception/std::get_terminate
- exception/std::get_unexpected
- exception/std::make_exception_ptr
- exception/std::rethrow_exception
- exception/std::set_terminate
- exception/std::set_unexpected
- exception/std::terminate
- exception/std::uncaught_exception
- exception/std::unexpected
ms.assetid: c09ac569-5e35-4fe8-872d-ca5810274dd7
helpviewer_keywords:
- std::current_exception [C++]
- std::get_terminate [C++]
- std::get_unexpected [C++]
- std::make_exception_ptr [C++]
- std::rethrow_exception [C++]
- std::set_terminate [C++]
- std::set_unexpected [C++]
- std::terminate [C++]
- std::uncaught_exception [C++]
- std::unexpected [C++]
ms.openlocfilehash: 4aab46fa771b88d1baad311aa631a57afce4911e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847831"
---
# <a name="ltexceptiongt-functions"></a>&lt;exception&gt; 함수

||||
|-|-|-|
|[current_exception](#current_exception)|[get_terminate](#get_terminate)|[get_unexpected](#get_unexpected)|
|[make_exception_ptr](#make_exception_ptr)|[rethrow_exception](#rethrow_exception)|[set_terminate](#set_terminate)|
|[set_unexpected](#set_unexpected)|[terminate](#terminate)|[uncaught_exception](#uncaught_exception)|
|[unexpected](#unexpected)|

## <a name="current_exception"></a>  current_exception

현재 예외에 대한 스마트 포인터를 가져옵니다.

```cpp
exception_ptr current_exception();
```

### <a name="return-value"></a>반환 값

현재 예외를 가리키는 [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) 개체입니다.

### <a name="remarks"></a>설명

catch 블록에서 `current_exception` 함수를 호출합니다. 예외가 발생하고 catch 블록이 예외를 catch할 경우, `current_exception` 함수는 예외를 참조하는 `exception_ptr` 개체를 반환합니다. 그렇지 않으면 인수가 null `exception_ptr` 개체를 반환합니다.

`current_exception` 함수는 `catch` 문이 [exception-declaration](../cpp/try-throw-and-catch-statements-cpp.md) 문을 지정하는지 여부와 관계없이 발생 중인 예외를 캡처합니다.

예외를 다시 throw하지 않는 경우 `catch`의 끝에서 현재 예외의 소멸자가 호출되지 않습니다. 그러나 소멸자에 있는`current_exception` 함수를 호출하는 경우, 함수는 현재 예외를 참조하는 `exception_ptr` 개체를 반환합니다.

`current_exception` 수식에 대한 연속 호출은 현재 예외 건의 다른 복사본을 뜻하는 `exception_ptr` 개체를 반환합니다. 따라서 개체는 복사본에 같은 이진 값이 있더라도 다른 복사본을 참조하기 때문에 같지 않은 것으로 비교합니다.

## <a name="make_exception_ptr"></a>  make_exception_ptr

예외 복사본이 들어 있는 [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) 개체를 생성합니다.

```cpp
template <class E>
exception_ptr make_exception_ptr(E Except);
```

### <a name="parameters"></a>매개 변수

`Except` 복사할 예외가 있는 클래스입니다. 모든 클래스 개체를 인수로 사용할 수 있지만, 일반적으로 [예외 클래스](../standard-library/exception-class.md) 개체를 `make_exception_ptr` 함수의 인수로 지정합니다.

### <a name="return-value"></a>반환 값

`Except`에 대한 현재 예외의 복사본을 가리키는 [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) 개체입니다.

### <a name="remarks"></a>설명

`make_exception_ptr` 함수 호출은 C++ 예외를 throw하고 catch 블록에서 catch한 다음 [current_exception](../standard-library/exception-functions.md#current_exception) 함수를 호출하여 예외를 참조하는 `exception_ptr` 개체를 반환하는 것과 동일합니다. `make_exception_ptr` 함수의 Microsoft 구현은 예외를 throw한 후 catch하는 것보다 더 효율적입니다.

응용 프로그램에는 일반적으로 `make_exception_ptr` 함수가 필요하지 않으며 이 함수를 사용하지 않는 것이 좋습니다.

## <a name="rethrow_exception"></a>  rethrow_exception

매개 변수로 전달되는 예외를 throw합니다.

```cpp
void rethrow_exception(exception_ptr P);
```

### <a name="parameters"></a>매개 변수

`P` 예외가 다시 throw 합니다. `P`가 null인 [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)인 경우 함수에서 [std::bad_exception](../standard-library/bad-exception-class.md)을 throw합니다.

### <a name="remarks"></a>설명

`exception_ptr` 개체에서 catch된 예외를 저장한 후 기본 스레드에서 개체를 처리할 수 있습니다. 기본 스레드에서 `rethrow_exception` 개체와 함께 작동하는 `exception_ptr` 함수를 호출합니다. `rethrow_exception` 함수는 `exception_ptr` 개체에서 예외를 추출하고, 주 스레드의 컨텍스트에서 예외를 throw합니다.

## <a name="get_terminate"></a>  get_terminate

현재 `terminate_handler` 함수를 가져옵니다.

```cpp
terminate_handler get_terminate();
```

## <a name="set_terminate"></a>  set_terminate

프로그램을 종료할 때 호출할 새 `terminate_handler`를 설정합니다.

```cpp
terminate_handler set_terminate(terminate_handler fnew) throw();
```

### <a name="parameters"></a>매개 변수

`fnew` 종료 시 호출할 함수입니다.

### <a name="return-value"></a>반환 값

종료 시 호출에 사용된 이전 함수의 주소입니다.

### <a name="remarks"></a>설명

함수는 새 [terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)를 함수 * `fnew`로 설정합니다. 따라서 `fnew`가 null 포인터가 아니어야 합니다. 함수는 이전 terminate 처리기의 주소를 반환합니다.

### <a name="example"></a>예제

```cpp
// exception_set_terminate.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>

using namespace std;

void termfunction()
{
    cout << "My terminate function called." << endl;
    abort();
}

int main()
{
    terminate_handler oldHandler = set_terminate(termfunction);

    // Throwing an unhandled exception would also terminate the program
    // or we could explicitly call terminate();

    //throw bad_alloc();
    terminate();
}

```

## <a name="get_unexpected"></a>  get_unexpected

현재 `unexpected_handler` 함수를 가져옵니다.

```cpp
unexpected_handler get_unexpected();
```

## <a name="set_unexpected"></a>  set_unexpected

예기치 않은 예외가 발생할 경우를 위해 새 `unexpected_handler`를 설정합니다.

```cpp
unexpected_handler set_unexpected(unexpected_handler fnew) throw();
```

### <a name="parameters"></a>매개 변수

`fnew` 예기치 않은 예외가 발견 되 면 호출 되는 함수입니다.

### <a name="return-value"></a>반환 값

이전 `unexpected_handler`의 주소입니다.

### <a name="remarks"></a>설명

`fnew`는 null 포인터가 아니어야 합니다.

C++ 표준의 경우 함수가 throw 목록에 없는 예외를 throw할 경우 `unexpected`가 호출되어야 합니다. 현재 구현은 이 기능을 지원하지 않습니다. 다음 예제에서는 `unexpected`를 직접 호출하고 나서 `unexpected_handler`를 호출합니다.

### <a name="example"></a>예제

```cpp
// exception_set_unexpected.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>

using namespace std;

void uefunction()
{
    cout << "My unhandled exception function called." << endl;
    terminate(); // this is what unexpected() calls by default
}

int main()
{
    unexpected_handler oldHandler = set_unexpected(uefunction);

    unexpected(); // library function to force calling the
                  // current unexpected handler
}

```

## <a name="terminate"></a>  terminate

종료 처리기를 호출합니다.

```cpp
void terminate();
```

### <a name="remarks"></a>설명

이 함수는 `void` 형식 함수인 terminate 처리기를 호출합니다. **terminate**가 프로그램에 의해 직접 호출될 경우 [set_terminate](../standard-library/exception-functions.md#set_terminate)에 대한 호출을 통해 가장 최근 설정된 terminate 처리기가 호출됩니다. throw 식 평가 중에 다른 여러 가지 이유로 **terminate**가 호출될 경우에는 throw 식을 평가한 직후 적용되는 terminate 처리기가 호출됩니다.

terminate 처리기는 호출자로 반환되지 않을 수 있습니다. 프로그램 시작 시 **abort**를 호출하는 함수가 terminate 처리기입니다.

### <a name="example"></a>예제

**terminate** 사용에 대한 예제는 [set_unexpected](../standard-library/exception-functions.md#set_unexpected)를 참조하세요.

## <a name="uncaught_exception"></a>  uncaught_exception

throw된 예외가 현재 처리 중인 경우에만 `true`를 반환합니다.

```cpp
bool uncaught_exception();
```

### <a name="return-value"></a>반환 값

throw 식 평가를 완료한 후, 그리고 일치하는 처리기에서 예외 선언 초기화를 완료하거나 throw 식의 결과로 [unexpected](../standard-library/exception-functions.md#unexpected)를 호출하기 전에 `true`를 반환합니다. 특히 `uncaught_exception`은 예외 해제 중에 호출되는 소멸자에서 호출된 경우 `true`를 반환합니다. 장치의 경우 `uncaught_exception`은 Windows Mobile 2005 플랫폼을 포함하여 Windows CE 5.00 이상 버전에서만 지원됩니다.

### <a name="example"></a>예제

```cpp
// exception_uncaught_exception.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>
#include <string>

class Test
{
public:
   Test( std::string msg ) : m_msg( msg )
   {
      std::cout << "In Test::Test(\"" << m_msg << "\")" << std::endl;
   }
   ~Test( )
   {
      std::cout << "In Test::~Test(\"" << m_msg << "\")" << std::endl
         << "        std::uncaught_exception( ) = "
         << std::uncaught_exception( )
         << std::endl;
   }
private:
    std::string m_msg;
};

// uncaught_exception will be true in the destructor
// for the object created inside the try block because
// the destructor is being called as part of the unwind.

int main( void )
   {
      Test t1( "outside try block" );
      try
      {
         Test t2( "inside try block" );
         throw 1;
      }
      catch (...) {
   }
}
```

```Output
In Test::Test("outside try block")
In Test::Test("inside try block")
In Test::~Test("inside try block")
        std::uncaught_exception( ) = 1
In Test::~Test("outside try block")
        std::uncaught_exception( ) = 0
```

## <a name="unexpected"></a>  unexpected

unexpected 처리기를 호출합니다.

```cpp
void unexpected();
```

### <a name="remarks"></a>설명

C++ 표준의 경우 함수가 throw 목록에 없는 예외를 throw할 경우 `unexpected`가 호출되어야 합니다. 현재 구현은 이 기능을 지원하지 않습니다. 이 예제에서는 unexpected 처리기를 호출하는 `unexpected`를 직접 호출합니다.

이 함수는 `void` 형식 함수인 unexpected 처리기를 호출합니다. `unexpected`가 프로그램에 의해 직접 호출될 경우 [set_unexpected](../standard-library/exception-functions.md#set_unexpected)에 대한 호출을 통해 가장 최근 설정된 unexpected 처리기가 호출됩니다.

unexpected 처리기는 호출자로 반환되지 않을 수 있습니다. 다음과 같은 경우 실행을 종료할 수 있습니다.

- 예외 사양에 나열된 형식의 개체 또는 unexpected 처리기가 프로그램에서 직접 호출될 경우 모든 형식의 개체를 throw할 경우.

- 형식 [bad_exception](../standard-library/bad-exception-class.md)의 개체를 throw할 경우.

- [terminate](../standard-library/exception-functions.md#terminate), **abort** 또는 **exit**(`int`)를 호출할 경우.

프로그램 시작 시 [terminate](../standard-library/exception-functions.md#terminate)를 호출하는 함수가 unexpected 처리기입니다.

### <a name="example"></a>예제

**unexpected** 사용에 대한 예제는 [set_unexpected](../standard-library/exception-functions.md#set_unexpected)를 참조하세요.

## <a name="see-also"></a>참고자료

[\<exception>](../standard-library/exception.md)<br/>
