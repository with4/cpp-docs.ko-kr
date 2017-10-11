---
title: "컴파일러 오류 C2797 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2797
dev_langs:
- C++
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 09c5a26a1a7bb594419d2db211f86074d01da84e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2797"></a>컴파일러 오류 C2797
(사용 되지 않음) 멤버 이니셜라이저 또는 비정적 데이터 멤버 이니셜라이저 내의 목록 초기화가 구현 되지 않았습니다.  
  
 이 경고는 Visual Studio 2015에서 사용 되지 않습니다. Visual Studio 2013 및 이전 버전의 Visual c + + 컴파일러는 멤버 이니셜라이저 목록 또는 비정적 데이터 멤버 이니셜라이저 내의 목록 초기화를 구현 하지 않습니다. Visual Studio 2013 업데이트 3 이전에는 이 초기화가 함수 호출로 자동 변환되어 잘못된 코드가 생성될 수 있었습니다. Visual Studio 2013 업데이트 3에서는 이러한 초기화를 오류로 보고합니다.  
  
 이 예제에서는 C2797 오류를 생성합니다.  
  
```  
#include <vector>  
struct S {  
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'  
  
    std::vector<int> v1;  
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'  
};  
  
```  
  
 또한 다음과 같이 C2797도 생성합니다.  
  
```  
struct S1 {  
    int i;  
};  
  
struct S2 {  
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664  
    S1 s1;  
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664  
};  
  
```  
  
 이 문제를 해결하려면 안쪽 목록의 명시적 생성을 사용할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
#include <vector>  
typedef std::vector<int> Vector;  
struct S {  
    S() : v1(Vector{1}) {}  
  
    Vector v1;  
    Vector v2 = Vector{1, 2};  
};  
  
```  
  
 목록 초기화를 수행할 필요가 없는 경우에는 다음과 같은 코드를 사용합니다.  
  
```  
struct S {  
    S() : s1("") {}  
  
    std::string s1;  
    std::string s2 = std::string("");  
};  
  
```  
  
 Visual Studio 2013 업데이트 3 이전 버전 Visual Studio 2013의 컴파일러는 이 작업을 암시적으로 수행합니다.
