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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 5eea0aae37627015f8723835e4e3e1cb0c6d2e94
ms.contentlocale: ko-kr
ms.lasthandoff: 04/24/2017

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
