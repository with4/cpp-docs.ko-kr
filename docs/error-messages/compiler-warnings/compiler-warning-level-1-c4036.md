---
title: "컴파일러 경고 (수준 1) C4036 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 30ff24d9d8746d914ba4dd098e715d8b5ecb55c9
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4036"></a>컴파일러 경고(수준 1) C4036
실제 매개 변수로 명명되지 않은 'type'입니다.  
  
 실제 매개 변수로 사용하는 구조체, 공용 구조체, 열거형 또는 클래스에 대해 형식 이름이 지정되지 않았습니다. 사용 중인 경우 [/Zg](../../build/reference/zg-generate-function-prototypes.md) 컴파일러 발생이 경고와를 주석으로 생성 된 프로토타입에서 정식 매개 변수 함수 프로토타입을 생성 합니다.  
  
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
