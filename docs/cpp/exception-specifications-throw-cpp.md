---
title: "예외 사양 (throw) (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 01/12/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c93fdaa75155e6f0117ef1c30d4e093d5ca0e576
ms.sourcegitcommit: c2e990450ccd528d85b2783fbc63042612987cfd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2018
---
# <a name="exception-specifications-throw-noexcept-c"></a>예외 사양 (throw, noexcept) (c + +)

예외 사양은 함수에 의해 전파 될 수 있는 예외 형식에 대해 프로그래머의 의도 표시 하는 c + + 언어 기능. 하는 함수 되거나 예외를 사용 하 여 종료 되지 않을 지정할 수는 *예외 사양이*합니다. 컴파일러는 함수에 대 한 호출을 최적화 하기 위해이 정보를 사용 하 고 예외가 발생된 하는 경우 프로그램을 종료 하려면 함수를 이스케이프 합니다. 

C + + 17 하기 전에 두 종류의 예외 사양이 없습니다. *noexcept 사양* C + + 11부터 였습니다. 함수를 이스케이프 될 수 있는 잠재적인 예외 집합이 비어 있는지 여부를 지정 합니다. *동적 예외 사양은*, 또는 `throw(optional_type_list)` 사양, C + + 11에서 더 이상 사용 되어을 제외 하 고 C + + 17과 제거 `throw()`, noexcept (true)에 대 한 별칭인 합니다. 이 예외 사양은 함수에서 예외를 throw 할 수 하는 방법에 대 한 요약 정보를 제공 하는데 실제로 문제가 있는 것으로 발견 된 합니다. 어느 정도 유용한 것으로 입증 된 하나의 동적 예외 사양을는 무조건 `throw()` 사양입니다. 예를 들어 함수 선언 합니다.

```cpp
void MyFunction(int i) throw();
```

 컴파일러에 함수가 아무 예외도 throw하지 않음을 알립니다. 그러나 **/std:c + + 14** 모드 초래할 수 정의 되지 않은 동작이 면 함수는 예외를 throw 합니다. 사용할 수 있는 권장 따라서는 [noexcept](../cpp/noexcept-cpp.md) 위와 대신 연산자:

```cpp
void MyFunction(int i) noexcept;
```

다음 표에는 예외 사양의 Visual C++ 구현이 요약되어 있습니다.

|예외 사양|의미|
|-----------------------------|-------------|
|`noexcept`<br>`noexcept(true)`<br>`throw()`|이 함수는 예외를 throw하지 않습니다. [/std:c + + 14](../build/reference/std-specify-language-standard-version.md) 모드 (기본값), `noexcept` 및 `noexcept(true)` 동일 합니다. 선언 된 함수에서 예외가 throw 됩니다 때 `noexcept` 또는 `noexcept(true)`, [std:: terminate](../standard-library/exception-functions.md#terminate) 가 호출 됩니다. 로 선언 된 함수에서 예외가 throw 됩니다 때 `throw()` 에 **/std:c + + 14** 모드, 결과 정의 되지 않은 동작이 있습니다. 특정 함수가 호출 됩니다. 이 컴파일러 호출에 필요한 표준 C + + 14에서 확산 [std::unexpected](../standard-library/exception-functions.md#unexpected)합니다.  <br> **Visual Studio 2017 버전 15.5 이상**:에서 **/std:c + + 17** 모드 `noexcept`, `noexcept(true)`, 및 `throw()` 모두 동일 합니다. **/std:c + + 17** 모드 `throw()` 별칭인 `noexcept(true)`합니다. **/std:c + + 17** 모드에서는 이러한 사양을 사용 하 여 선언 된 함수에서 예외가 throw 되 면 [std:: terminate](../standard-library/exception-functions.md#terminate) 호출 되는 C + + 17 표준에 필요 합니다.|
|`noexcept(false)`<br/>`throw(...)`<br/>사양이 없는|함수는 모든 형식의 예외를 throw 할 수 있습니다.|
|`throw(type)`| (**C + + 14 및 이전 버전**) 함수 형식의 예외를 throw 할 수 있습니다 `type`합니다. Microsoft c + + 컴파일러는 구문를 허용 하지만로 해석 `noexcept(false)`합니다. **/std:c + + 17** 모드 컴파일러 경고가 C5040 발생 합니다.|

 예외 처리 응용 프로그램을 사용 하는 함수에에서 있어야 함수 외부 범위를 종료 하기 전에 예외를 throw 하는 핸들을 표시 하는 호출 스택을 `noexcept`, `noexcept(true)`, 또는 `throw()`합니다. 예외를 throw 하 한 및 예외를 처리 하는 것으로 지정 된 함수 사이 호출 하는 경우 `noexcept`, `noexcept(true)` (또는 `throw()` 에 **/std:c + + 17** 모드), 경우 프로그램이 종료 되 고 noexcept 함수가 예외를 전파합니다.

 예외 동작 함수는 다음 요인에 따라 달라 집니다.

- [언어 표준 컴파일 모드](../build/reference/std-specify-language-standard-version.md) 설정 됩니다.
- C 또는 C++에서 함수를 컴파일하는지 여부

- [/EH](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용 합니다.

- 예외 사양을 명시적으로 지정하는지 여부

 C 함수에서는 명시적 예외 사양이 허용되지 않습니다. C 함수 아닌 것으로 가정에서 예외를 throw **/EHsc**, 아래에서 구조화 된 예외를 throw 할 수 있습니다 및 **/EHs**, **/EHa**, 또는 **/EHac**합니다.

 다음 표에서 c + + 함수는 다양 한 컴파일러 예외 처리 옵션 아래에서 잠재적으로 throw 할 수 있습니다 하는 여부가 요약 되어 있습니다.

|함수|/EHsc|/EHs|/EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|예외 사양이 없는 C++ 함수|예|예|예|예|
|C + + 함수 `noexcept`, `noexcept(true)`, 또는 `throw()` 예외 사양|아니요|아니요|예|예|
|C + + 함수 `noexcept(false)`, `throw(...)`, 또는 `throw(type)` 예외 사양|예|예|예|예|

## <a name="example"></a>예

```cpp
// exception_specification.cpp
// compile with: /EHs
#include <stdio.h>

void handler() {
   printf_s("in handler\n");
}

void f1(void) throw(int) {
   printf_s("About to throw 1\n");
   if (1)
      throw 1;
}

void f5(void) throw() {
   try {
      f1();
   }
   catch(...) {
      handler();
    }
}

// invalid, doesn't handle the int exception thrown from f1()
// void f3(void) throw() {
//   f1();
// }

void __declspec(nothrow) f2(void) {
   try {
      f1();
   }
   catch(int) {
      handler();
    }
}

// only valid if compiled without /EHc 
// /EHc means assume extern "C" functions don't throw exceptions
extern "C" void f4(void);
void f4(void) {
   f1();
}

int main() {
   f2();

   try {
      f4();
   }
   catch(...) {
      printf_s("Caught exception from f4\n");
   }
   f5();
}
```

```Output
About to throw 1
in handler
About to throw 1
Caught exception from f4
About to throw 1
in handler
```

## <a name="see-also"></a>참고 항목

 [시도, throw 및 catch 문 (c + +)](../cpp/try-throw-and-catch-statements-cpp.md) [c + + 예외 처리](../cpp/cpp-exception-handling.md)