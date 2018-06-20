---
title: extern (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 04/12/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- extern
- extern_CPP
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00b9f94d02443163f45b83d64702fe49622597cd
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261079"
---
# <a name="extern-c"></a>extern (c + +)

**extern** 키워드가 해당 작업의 이름에 있는지를 지정 하려면 전역 변수, 함수 또는 템플릿 선언에 적용 되는지 *외부 링크*합니다. 링크 및 전역 변수의 사용은 권장 되지 않습니다 배경 정보를 참조 하십시오. [프로그램 및 링크](program-and-linkage-cpp.md)합니다.

**extern** 키워드는 컨텍스트에 따라 4 개의 의미를 갖습니다.

1. 비 const 전역 변수 선언에 **extern** 다른 변환 단위에서 변수 또는 함수 정의 되도록 지정 합니다. **extern** 변수가 정의 된 노드를 제외한 모든 파일에 적용 되어야 합니다.
1. const 변수 선언에 변수에 외부 링크가 지정 합니다. **extern** 모든 파일의 모든 선언에 적용 되어야 합니다. (전역 상수 변수는 내부 링크를 기본적으로 합니다.)
1. **extern "C"** 함수 다른 곳에 정의 C 언어 호출 규칙을 사용 하도록 지정 합니다. Extern "C" 한정자 블록에 여러 함수 선언에도 적용 될 수 있습니다.
1. 템플릿 선언에는 템플릿을 이미 인스턴스화된 다른 위치를 지정 합니다. 현재 위치에 새로 만드는 대신 다른 인스턴스화 다시 사용할 수 있는 컴파일러에 지시 하는 최적화입니다. 이 사용이에 대 한 자세한 내용은 **extern**, 참조 [템플릿](templates-cpp.md)합니다.

## <a name="extern-linkage-for-non-const-globals"></a>비 const globals extern 링크

링커 표시 하는 경우 **extern** 전역 변수 선언 하기 전에 다른 변환 단위에서 정의 대 한 찾습니다. 전역 범위에서 비 const 변수 선언을 기본적으로 외부 에 적용 **extern** 정의 제공 하지 않는 선언에 있습니다.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
extern int i;  // declaration only. same as i in FileA

//fileC.cpp
extern int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
extern int i = 43; // same error (extern is ignored on definitions)
```

## <a name="extern-linkage-for-const-globals"></a>extern const globals 링크

A **const** 전역 변수는 기본적으로 내부 링크를 가집니다. 변수 외부 링크를 적용는 **extern** 키워드를 다른 파일에 있는 다른 모든 선언에 대 한도 정의 합니다.

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>Extern constexpr 링크

Visual Studio 2017 15.3 및 이전 버전의에서 컴파일러 항상 겠지만 constexpr 변수 내부 링크가 변수 extern으로 표시 된 경우에 합니다. Visual Studio 2017 15.5 버전에서 새 컴파일러 스위치([/Zc:externConstexpr](../build/reference/zc-externconstexpr.md))는 올바른 표준 준수 동작을 활성화합니다. 결국 이는 기본값이 됩니다.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

표시 되어야 하는 데 필요한 헤더 파일에 선언 된 변수 extern constexpr이 있으면 **__declspec (selectany)** 올바르게 결합 해당 중복 선언 하려면:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>extern "C" 및 extern "c + +" 함수 선언

 C + +에서는 문자열에서 사용 하는 경우 **extern** 다른 언어의 링크 규칙이 선언 자에 사용 되 고 있는지를 지정 합니다. C 함수 및 데이터는 이전에 C 링크가 있는 것으로 선언된 경우에만 액세스할 수 있습니다. 단, 별도로 컴파일된 변환 단위로 정의되어야 합니다.

 Microsoft c + +에서는 문자열 **"C"** 및 **"c + +"** 에 *문자열 리터럴* 필드입니다. 모든 표준 포함 파일의 **extern** "C" 구문을 런타임 라이브러리 함수를 c + + 프로그램에서 사용할 수 있도록 합니다.

## <a name="example"></a>예

다음 예제에서는 C 링크가 있는 이름을 선언 하는 방법을 보여 줍니다.

```cpp
// Declare printf with C linkage.
extern "C" int printf(const char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
extern "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
extern "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions 
//  ShowChar and GetChar with C linkage.
extern "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

extern "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
extern "C" int errno;
```

 함수에 둘 이상의 링크 사양이 있는 경우 두 사양은 일치해야 합니다. C 및 C++ 링크가 둘 다 있는 것으로 함수를 선언하면 오류가 발생합니다. 뿐만 아니라 함수에 대한 두 선언(링크 사양이 있는 선언과 없는 선언)이 프로그램에서 발생할 경우 링크 사양이 있는 선언이 첫 번째여야 합니다. 이미 링크 사양이 있는 함수의 모든 중복 선언에는 첫 번째 선언에서 지정된 링크가 제공됩니다. 예를 들어:

```cpp
extern "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
extern "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>참고 항목

- [키워드](../cpp/keywords-cpp.md)
- [프로그램 및 링크](program-and-linkage-cpp.md)
- [extern c에서 저장소 클래스 지정자](../c-language/extern-storage-class-specifier.md) 
- [C에서 식별자 동작](../c-language/behavior-of-identifiers.md) 
- [C 링크](../c-language/linkage.md)