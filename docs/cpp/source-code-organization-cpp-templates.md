---
title: 소스 코드 조직 (c + + 템플릿) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
caps.latest.revision: 5
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b543ed2334640b9f7bac7250b1dc055504d7edf
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="source-code-organization-c-templates"></a>소스 코드 조직 (c + + 템플릿)

클래스 템플릿은 정의할 때 멤버 정의 해야 할 때 컴파일러에 게 표시 되는 방식으로 소스 코드를 구성 해야 합니다.   사용 하 여 선택할 수 있습니다는 *포함 모델* 또는 *명시적 인스턴스화* 모델입니다. 포함 모델 템플릿을 사용 하는 모든 파일의 멤버 정의 포함 합니다. 이 방법을 사용이 가장 간단 하 고 구체적인 유형을 템플릿과 함께 사용할 수 측면에서 최대한의 유연성을 제공 합니다. 단점은 컴파일 시간을 늘릴 수 있는 것입니다. 프로젝트 클 수 있지만 영향 및/또는 자체 포함 된 파일에는 큰 명시적 인스턴스화 접근 방식으로 템플릿 자체는 구체적 클래스 멤버 또는 특정 형식에 대 한 클래스 멤버를 인스턴스화합니다.  이 방법은 수 컴파일 시간이 속도가 향상 되지만 사용 클래스에만 해당 템플릿을 구현자 미리 설정한 제한 합니다. 일반적으로 컴파일 시간이 문제가 되는 경우가 아니면 포함 모델을 사용 하는 것이 좋습니다.

## <a name="background"></a>배경

서식 파일 컴파일러는 서식 파일 또는 해당 멤버에 대 한 개체 코드를 생성 하지 않는 의미에서 일반 클래스와는 다릅니다. 구체적인 형식으로 템플릿이 인스턴스화될 때까지 생성 하는 일은 없습니다. 발생 했을 때 컴파일러는 템플릿 인스턴스화에 같은 `MyClass<int> mc;` 해당 서명 없는 클래스가 있습니다. 아직 새 클래스를 생성 합니다. 또한 사용 되는 모든 멤버 함수에 대 한 코드를 생성 하려고 합니다. 이러한 정의 되지 않은 파일이 있는 # 컴파일 중인.cpp 파일에 included, 직접 또는 간접적으로 컴파일러 내용을 볼 수 없습니다.  컴파일러의 관점에서이 아닙니다 반드시 오류가 있는 경우 링커는 찾을 다른 변환 단위의 함수를 정의할 수 있습니다.  해당 코드를 찾지 못하면 링커 경우 발생 한 **확인 되지 않은 외부** 오류입니다.

## <a name="the-inclusion-model"></a>포함 모델

템플릿 정의 변환 단위 전체에 표시 되도록 하는 단순 하 고 가장 일반적인 방법은 헤더 파일 자체의 정의 넣는 것입니다.  서식 파일을 사용 하는 모든.cpp 파일을 단순히에 #include 헤더입니다. 표준 라이브러리에서 사용 하는 방법입니다.

```cpp
#ifndef MYARRAY
#define MYARRAY
#include <iostream>

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    // Full definitions:
    MyArray(){}
    void Print()
    {
        for (const auto v : arr)
        {
            std::cout << v << " , ";
        }
    }

    T& operator[](int i)
   {
       return arr[i];
   } 
};
#endif
```

이 방법을 사용 컴파일러는 완전 한 템플릿 정의에 액세스할 수 있으며 서식 파일 요청 시 모든 형식에 대 한를 인스턴스화할 수입니다. 것은 단순 하 고 비교적 쉽게 관리할 수 있습니다. 그러나 포함 모델에는 컴파일 시간 측면에서 비용이 있습니다.   이 비용은 큰 프로그램에서 문제가 될 수 경우에 특히 템플릿 헤더 자체 #includes 다른 헤더입니다. 모든.cpp 파일을 #includes 헤더 함수 템플릿 및 모든 정의의 자체 복사본을 받습니다. 링커는 일반적으로 함수에 대 한 여러 정의 종료 하지 마십시오 하지만이 작업을 수행 하는 데는 시간이 작업을 정렬할 수 없습니다. 더 작은 프로그램 중요 하지 않을 추가 컴파일 시간입니다.

## <a name="the-explicit-instantiation-model"></a>명시적 인스턴스화 모델

포함 모델 프로젝트에 대해 작동 하지 않는 경우 템플릿을 인스턴스화할를 사용 하는 형식 집합 확실히 알면.h 및.cpp 파일에 템플릿 코드를 분리할 및.cpp 파일에서 템플릿을 명시적으로 인스턴스화할 수 있습니다. 이렇게 하면 개체 코드를 생성할 컴파일러 사용자 인스턴스화를 발견 하면 표시 됩니다.

명시적 인스턴스화를 인스턴스화하 려는 엔터티의 서명 뒤 키워드 템플릿을 사용 하 여 만듭니다. 이 형식이 나 멤버 수 있습니다. 형식을 명시적으로 인스턴스화할 경우 모든 멤버가 인스턴스화됩니다.

```cpp
template MyArray<double, 5>;
```

```cpp
//MyArray.h
#ifndef MYARRAY
#define MYARRAY

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    MyArray();
    void Print();
    T& operator[](int i);
};
#endif

//MyArray.cpp
#include "stdafx.h"
#include <iostream>
#include "MyArray.h"

using namespace std;

template<typename T, size_t N>
MyArray<T,N>::MyArray(){}

template<typename T, size_t N>
void MyArray<T,N>::Print()
{
    for(const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

이전 예제에서는 명시적 인스턴스화는.cpp 파일의 맨 아래에 있습니다. A `MyArray` 에 대해서만 사용할 수 있습니다 **double** 또는 **문자열** 형식입니다.

> [!NOTE]
> C + + 11에서에서 **내보내기** 키워드 템플릿 정의의 컨텍스트에서 사용 되지 않습니다. 실제로이 영향을 미치지 거의 대부분의 컴파일러에서 되지 지원 합니다.
