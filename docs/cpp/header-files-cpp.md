---
title: 헤더 파일 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 04/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- header files [C++]
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b571cd2836e66ebef21898af27cf2a6d7082e0e5
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261069"
---
# <a name="header-files-c"></a>헤더 파일 (c + +)

변수, 함수, 클래스, 등과 같은 프로그램 요소 이름 사용 하려면 먼저 선언 되어야 합니다. 방금 쓸 수 없습니다 예를 들어 `x = 42` 첫 번째 'x'를 선언 하지 않고 있습니다. 

```cpp
int x; // declaration
x = 42; // use x
```

 선언은 컴파일러가 여부는 **int**, **double**, **함수**, **클래스** 또는 다른 작업입니다.  또한 각 이름은 선언 되어야 합니다 (직접 또는 간접적으로)에 사용 되는 모든.cpp 파일. 프로그램을 컴파일할 때 각.cpp 파일은 컴파일됩니다 하지 독립적으로 컴파일 단위에. 컴파일러는 어떤 이름이 다른 컴파일 단위에서 선언 된 인식 하지 못합니다. 즉, 클래스 또는 함수 또는 전역 변수를 정의 하는 경우이 사용 하는 각 추가.cpp 파일에서 해당 항목의 선언을 제공 해야 합니다. 해당 일의 각 선언은 모든 파일에 정확히 동일 해야 합니다. 약간의 불일치 링커 단일 프로그램에 모든 컴파일 단위를 병합 하려고 할 때 오류 또는 의도 하지 않은 동작이 발생 합니다.

C + +에는 규칙을 사용 하 여 오류에 대 한 가능성을 최소화 하려면 채택 *헤더 파일* 선언을 포함 하도록 합니다. 헤더 파일에 선언을 수행한 다음 사용 하는 # 모든.cpp 파일의 include 지시문 또는 기타 헤더 파일에 해당 선언이 필요 합니다. # 컴파일 전에.cpp 파일에 직접 지시문 삽입 하는 헤더 파일의 복사본을 include 합니다. 

## <a name="example"></a>예

다음 예제에서는 클래스를 선언 하 고 다음 다른 소스 파일에서 사용 하는 일반적인 방법은 보여 줍니다. 헤더 파일을 시작 합니다 **my_class.h**합니다. 클래스 정의 포함 하지만 정의 불완전 합니다. 멤버 함수 `do_something` 정의 되어 있지 않습니다.

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

다음으로 (일반적으로.cpp 유사한 확장)와 구현 파일을 만듭니다. 에서는 파일 my_class.cpp 호출 하 고 멤버 선언에 대 한 정의 제공 합니다. 추가 `#include` 삽입 my_class 선언을 가지려면 "my_class.h" 파일에 대 한 지시문이 시점에서.cpp 파일 및 म 포함  **\<iostream >** 의 선언에 끌어올 `std::cout`합니다. Note 따옴표는 소스 파일과 동일한 디렉터리에 대 한 헤더 파일에 대 한 사용 및 표준 라이브러리 헤더에 꺾쇠 괄호 사용 됩니다. 또한 많은 표준 라이브러리 헤더 없는.h 또는 기타 파일 확장명입니다.

구현 파일에서에서는 선택적으로 사용할 수는 **를 사용 하 여** 와 "my_class" 또는 "cout"의 모든 내용을 한 정하는 것을 방지 하려면 문을 "n::" 또는 "std::".  넣지 마세요 **를 사용 하 여** 헤더 파일에는 문을!

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

사용 하는 이제 `my_class` 다른.cpp 파일에 있습니다. म # 컴파일러가 선언에 끌어와 있도록 헤더 파일 include 합니다. 모든 컴파일러 요구를 알고은 해당 my_class를 호출 하는 공용 멤버 함수를 가진 `do_something()`합니다.

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

각.cpp 파일을.obj 파일로 컴파일하 컴파일러 끝나면.obj 파일을 링커에 전달 합니다. 찾으면 my_class;에 대 한 정확히 하나의 정의 링커 개체 파일을 병합 하는 경우 생성 my_class.cpp에 대 한.obj 파일에 있으며 빌드가 성공 하면 됩니다.

## <a name="include-guards"></a>Include 가드

일반적으로 헤더 파일에는 한 *include 가드* 또는 **#pragma 한 번** 지시문은 삽입 되 게 하지 여러 번 단일.cpp 파일로 합니다. 

my_class.h
#<a name="ifndef-myclassh--include-guard"></a>ifndef MY_CLASS_H / include 가드 /
#<a name="define-myclassh"></a>MY_CLASS_H 정의


네임 스페이스 N {my_class 클래스 {공용: void do_something();을 (를);

}

#<a name="endif--myclassh-"></a>endif / * MY_CLASS_H * /

## <a name="what-to-put-in-a-header-file"></a>헤더 파일에 삽입할 항목에

헤더 파일은 여러 파일에 의해 잠재적으로 포함 될 수 있습니다, 때문에 이름이 동일한 정의가 여러 개 생성 될 수 있습니다는 정의 포함할 수 없습니다. 다음은 허용 되지 않거나 매우 좋지 않은 방법으로 간주 됩니다.

- 네임 스페이스 또는 전역 범위에서 기본 제공 형식 정의
- 비인라인 함수 정의 
- 비 const 변수 정의
- 집계 정의
- 명명되지 않은 네임스페이스
- using 지시문

사용은 **를 사용 하 여** 지시문은 오류를 반드시 발생 하지 것입니다 되지만 직접 또는 간접적으로 해당 헤더를 포함 하는 모든.cpp 파일의 범위 내에 네임 스페이스를 제공 하기 때문에 문제가 발생할 수 있습니다. 

## <a name="sample-header-file"></a>샘플 헤더 파일

다음 예제에서는 다양 한 종류의 선언 및 헤더 파일에 허용 되는 정의 보여 줍니다.

```cpp
#pragma once 
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{

    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };


    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif


    class my_class   // regular class definition, 
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;

}
