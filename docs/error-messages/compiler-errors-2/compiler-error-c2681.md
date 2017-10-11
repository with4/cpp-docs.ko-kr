---
title: "컴파일러 오류 C2681 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2681
dev_langs:
- C++
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9978a520b4682e4e2c7c4856d4e42675be0ab901
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2681"></a>컴파일러 오류 C2681
'type': 이름에 대 한 잘못 된 식 형식  
  
 캐스팅 연산자를 잘못 된 형식에서 변환 하려고 했습니다. 예를 들어, 사용 하는 경우는 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 포인터 형식으로 소스 식은 식을 변환 연산자는 포인터 여야 합니다.  
  
 다음 샘플에서는 C2681 오류가 생성 됩니다.  
  
```  
// C2681.cpp  
class A { virtual void f(); };  
  
void g(int i) {  
    A* pa;  
    pa = dynamic_cast<A*>(i);  // C2681  
}  
```
