---
title: 컴파일러 오류 C2503 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2503
dev_langs:
- C++
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db11113b7f6061a7e3464cc69ae1f397fc7a4753
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2503"></a>컴파일러 오류 C2503
'class': 기본 클래스에는 크기가 0 인 배열을 포함할 수 없습니다  
  
 기본 클래스 또는 구조체에 크기가 0 인 배열이 포함 되어 있습니다. 클래스에서 배열에 요소가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C2503 오류가 생성 됩니다.  
  
```  
// C2503.cpp  
// compile with: /c  
class A {  
   public:  
   int array [];  
};  
  
class B : A {};    // C2503  
  
class C {  
public:  
   int array [10];  
};  
  
class D : C {};  
```