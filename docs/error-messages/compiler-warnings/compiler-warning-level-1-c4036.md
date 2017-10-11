---
title: "컴파일러 경고 (수준 1) C4036 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4036
dev_langs:
- C++
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6392ba12c14ca3ef89f992e358bf019d1d92e5db
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4036"></a>컴파일러 경고(수준 1) C4036
실제 매개 변수로 명명되지 않은 'type'입니다.  
  
 실제 매개 변수로 사용하는 구조체, 공용 구조체, 열거형 또는 클래스에 대해 형식 이름이 지정되지 않았습니다. 함수 프로토타입을 생성하는 데 [/Zg](../../build/reference/zg-generate-function-prototypes.md) 를 사용하고 있는 경우 컴파일러에서 이 경고를 발생시키고 생성된 프로토타입에서 정식 매개 변수를 주석으로 처리합니다.  
  
 이 경고를 해결하려면 형식 이름을 지정합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4036을 생성합니다.  
  
```  
// C4036.c  
// compile with: /Zg /W1  
// D9035 expected  
typedef struct { int i; } T;  
void f(T* t) {}   // C4036  
  
// OK  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```
