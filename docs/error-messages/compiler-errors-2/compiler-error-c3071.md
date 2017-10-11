---
title: "컴파일러 오류 C3071 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3071
dev_langs:
- C++
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fc5cca3bdb0ff10f9f11c89ed3193002ebc884b0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3071"></a>컴파일러 오류 C3071
'operator' 연산자는 ref 클래스 또는 값 형식의 인스턴스에만 적용할 수 있습니다.  
  
 CLR 연산자는 네이티브 형식에 사용할 수 없습니다. 이 연산자는 ref 클래스나 ref 구조체(값 형식)에 사용할 수 있으며 int 같은 네이티브 형식이나 네이티브 형식에 대한 별칭(예: System::Int32)에는 사용할 수 없습니다. 이러한 형식은 C++ 코드에서 네이티브 변수를 참조하는 방식으로 boxing될 수 없기 때문에, 이 연산자를 사용할 수 없습니다.  
  
 자세한 내용은 참조 [추적 참조 연산자](../../windows/tracking-reference-operator-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3071 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3071.cpp  
// compile with: /clr  
class N {};  
ref struct R {};  
  
int main() {  
   N n;  
   %n;   // C3071  
  
   R r;  
   R ^ r2 = %r;   // OK  
}  
```
