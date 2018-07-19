---
title: novtable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- novtable_cpp
dev_langs:
- C++
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad0c50330d174a6139ce6e588b278e03cd99562
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944575"
---
# <a name="novtable"></a>novtable
## <a name="microsoft-specific"></a>Microsoft 전용  
 이 **__declspec** 확장 된 특성입니다.  
  
 이러한 형태의 **__declspec** 모든 클래스 선언에 적용할 수 있지만 순수 인터페이스 클래스, 즉, 자체적으로 인스턴스화되지 않을 하는 클래스에만 적용 해야 합니다. 합니다 **__declspec** 컴파일러가 생성자와 클래스의 소멸자에서 vfptr을 초기화 하는 코드 생성을 중지 합니다. 대부분의 경우 이렇게 하면 클래스와 연결된 vtable에 대한 참조만 제거되므로 링커가 이를 제거합니다. 이 형식은 사용 하 여 **__declspec** 코드 크기가 상당히 감소 될 수 있습니다.  
  
 `novtable`로 표시된 클래스를 인스턴스화한 다음 클래스 멤버에 액세스하려고 하면 AV(액세스 위반)가 발생합니다.  
  
## <a name="example"></a>예  
  
```cpp 
// novtable.cpp  
#include <stdio.h>  
  
struct __declspec(novtable) X {  
   virtual void mf();  
};  
  
struct Y : public X {  
   void mf() {  
      printf_s("In Y\n");  
   }  
};  
  
int main() {  
   // X *pX = new X();  
   // pX->mf();   // Causes a runtime access violation.  
  
   Y *pY = new Y();  
   pY->mf();  
}  
```  
  
```Output  
In Y  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)