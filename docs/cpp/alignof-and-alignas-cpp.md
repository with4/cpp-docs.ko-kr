---
title: alignof 및 alignas (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e2988d1260cac91e2614765aba8ae1b9be9b922
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="alignof-and-alignas-c"></a>alignof 및 alignas(C++)
`alignas` 형식 지정자는 변수 및 사용자 정의 형식의 사용자 지정 맞춤을 지정하는 포팅 가능한 C++ 표준 방법입니다. 마찬가지로 `alignof` 연산자도 지정된 형식 또는 변수의 맞춤을 얻는 포팅 가능한 표준 방법입니다.  
  
## <a name="example"></a>예제  
 클래스, 구조체/공용 구조체 또는 개별 멤버에 `alignas`를 사용할 수 있습니다. 여러 `alignas` 지정자가 발견되는 경우 컴파일러는 가장 엄격한 지정자(가장 큰 값을 가진 지정자)를 선택합니다.  
  
```cpp  
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  

int main()
{  
    std::cout << alignof(Bar) << std::endl; // output: 16  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [맞춤](../cpp/alignment-cpp-declarations.md)