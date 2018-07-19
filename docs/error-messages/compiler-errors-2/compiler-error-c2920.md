---
title: 컴파일러 오류 C2920 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2920
dev_langs:
- C++
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18a2ccc8809b18d9a28b1fc60f5460dd4272a49c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244238"
---
# <a name="compiler-error-c2920"></a>컴파일러 오류 C2920
재정의: 'class' : 클래스 템플릿 또는 제네릭이(가) 이미 'type'(으)로 선언되었습니다.  
  
 제네릭 또는 템플릿 클래스에 동일하지 않은 선언이 여러 개 있습니다. 이 오류를 해결하려면 형식에 따라 다른 이름을 사용하거나 형식 이름의 재정의를 제거하세요.  
  
 다음 샘플에서는 C2920을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2920.cpp  
// compile with: /c  
typedef int TC1;  
template <class T>   
struct TC1 {};   // C2920  
struct TC2 {};   // OK - fix by using a different name  
```  
  
 C2920은 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2920b.cpp  
// compile with: /clr /c  
typedef int GC1;  
generic <class T>   
ref struct GC1 {};   // C2920  
ref struct GC2 {};   // OK - fix by using a different name  
```