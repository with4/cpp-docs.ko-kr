---
title: noinline | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noinline_cpp
dev_langs:
- C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37098e904402a42f6ff28e594db265fc07b4d458
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944554"
---
# <a name="noinline"></a>noinline
## <a name="microsoft-specific"></a>Microsoft 전용  
 **__declspec(noinline)** 컴파일러 인라인에 특정 멤버 함수 (클래스의 함수)을 지시 합니다.  
  
 함수가 작고 코드 성능에 심각한 영향을 주지 않는 경우 함수를 인라인 처리하지 않는 것이 적합할 수 있습니다. 즉, 오류 조건을 처리하는 함수처럼 함수가 작고 자주 호출될 가능성이 적은 경우가 여기에 해당합니다.  
  
 에 유의 하는 함수 표시 되 면 **noinline**를 호출 하는 함수 됩니다 더 작은 그 자체가 컴파일러 인라인 처리에 대 한 후보입니다.  
  
```cpp 
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [inline, __inline, \__forceinline](inline-functions-cpp.md)

