---
title: "컴파일러 오류 C2600 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2600
dev_langs: C++
helpviewer_keywords: C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 407598a68df37aa130ce26e4f02e98de975ab527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2600"></a>컴파일러 오류 C2600
'function': 컴파일러 생성 특수 멤버 함수를 정의할 수 없습니다. 먼저 클래스에서 선언되어야 합니다.  
  
 클래스에 대해 생성자나 소멸자와 같은 멤버 함수를 정의하려면 먼저 클래스에서 해당 함수를 선언해야 합니다. 클래스에 생성자나 소멸자가 선언되어 있지 않으면 컴파일러가 기본 생성자 및 소멸자(특수 멤버 함수)를 생성할 수 있습니다. 그러나 클래스에 일치하는 선언이 없는 상태로 이러한 함수 중 하나를 정의하면 컴파일러가 충돌을 검색합니다.  
  
 이 오류를 해결하려면 클래스 선언에서 클래스 선언 외부에 정의할 각 멤버 함수를 선언합니다.  
  
 다음 샘플에서는 C2600 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```