---
title: 컴파일러 경고 (수준 1) C4584 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4584
dev_langs:
- C++
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df3f92142fe42451ca7ae8272463d9347a263121
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4584"></a>컴파일러 경고(수준 1) C4584
'class1': 기본 'class2' 클래스는 이미 'class3'의 기본 클래스  
  
 사용자가 정의한 클래스 중 하나는 다른에서 상속 하는 두 개의 클래스에서 상속 합니다. 예를 들어:  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 이 경우에 경고가 발생 합니다. 클래스 C에 모두 클래스 A와 B 1. 클래스에서 상속 하 고 클래스에서 상속 되므로 이 경고는로 이러한 기본 클래스에서 멤버를 사용 하는 정규화 해야 하거나 참조 하는 클래스 멤버에 대 한 모호성으로 인해 컴파일러 오류가 생성 됩니다.