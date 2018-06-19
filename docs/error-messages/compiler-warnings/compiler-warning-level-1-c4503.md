---
title: 컴파일러 경고 (수준 1) C4503 | Microsoft Docs
ms.custom: ''
ms.date: 05/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f60fdb44c5368ccc5c5f089002614332d95a63fe
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255676"
---
# <a name="compiler-warning-level-1-c4503"></a>컴파일러 경고(수준 1) C4503

> '*식별자*': 데코레이팅된 이름 길이 초과 했으므로 이름이 잘립니다

## <a name="remarks"></a>설명

이 컴파일러 경고가 사용 되지 않으며 Visual Studio 2017 및 이후 컴파일러에서 생성 되지 않습니다.

데코 레이트 된 이름 (4096) 컴파일러 한계를 초과 하 고 잘렸습니다. 이 경고와는 잘림을 방지 하려면 인수 개수 개 사용 되는 식별자의 이름 길이 줄이십시오. 데코레이팅된 적용 해시 있는 컴파일러 한계 보다 더 이상 없고 이름 충돌이 발생할 수 있음 되지 않은 이름입니다.

코드 서식 파일을 포함 하는 경우이 경고를 발생 수는 이전 버전의 Visual Studio를 사용 하는 경우 특수화 된 반복 해 서 합니다. 예를 들어 지도 (표준 c + + 라이브러리)에서 맵. 이 상황에서 만들 수 있습니다 프로그램 typedef 형식 (한 **구조체**예를 들면) 해당 맵을 포함 하는 합니다.

그러나 코드를 재구성 하지 결정할 수도 있습니다.  C4503을 생성 하는 응용 프로그램을 출시할 수 있지만 잘린된 기호에 링크 타임 오류를 발생 한 경우 오류에 기호의 형식을 결정 하는 것이 어려울 수 있습니다. 또한 년 5 월 디버깅 하기가 어려울; 디버거 형식 이름에 문제가 많은 것 매핑 기호 이름이 있을 수 있습니다. 그러나 프로그램의 정확성 영향을 받지 않습니다 잘린된 이름입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4503 Visual Studio 2017 전에 컴파일러에서 생성 됩니다.

```cpp
// C4503.cpp
// compile with: /W1 /EHsc /c
// C4503 expected
#include <string>
#include <map>

class Field{};

typedef std::map<std::string, Field> Screen;
typedef std::map<std::string, Screen> WebApp;
typedef std::map<std::string, WebApp> WebAppTest;
typedef std::map<std::string, WebAppTest> Hello;
Hello MyWAT;
```

이 샘플에 C4503를 해결 하려면 코드를 다시 작성 하는 방법을 보여 줍니다.

```cpp
// C4503b.cpp
// compile with: /W1 /EHsc /c
#include <string>
#include <map>

class Field{};

struct Screen2 {
   std::map<std::string, Field> Element;
};

struct WebApp2 {
   std::map<std::string, Screen2> Element;
};

struct WebAppTest2 {
   std::map<std::string, WebApp2> Element;
};

struct Hello2 {
   std::map<std::string, WebAppTest2> Element;
};

Hello2 MyWAT2;
```