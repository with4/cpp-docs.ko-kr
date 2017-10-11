---
title: "컴파일러 오류 C3154 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3154
dev_langs:
- C++
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: de38898f775d621edfec464de8a51d20c3bdb4f0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3154"></a>컴파일러 오류 C3154
예상 ',' 줄임표 앞입니다. 비 쉼표로 구분 줄임표 매개 변수 배열 함수에서 지원 되지 않습니다.  
  
 가변 인수 함수를 올바르게 선언 되지 않았습니다.  
  
 자세한 내용은 참조 [가변 인수 목록 (...) (C + + /CLI CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3154 오류가 발생 합니다.  
  
```  
// C3154.cpp  
// compile with: /clr  
ref struct R {  
   void Func(int ... array<int> ^);   // C3154  
   void Func2(int i, ... array<int> ^){}   // OK  
   void Func3(array<int> ^){}   // OK  
   void Func4(... array<int> ^){}   // OK  
};  
  
int main() {  
   R ^ r = gcnew R;  
   r->Func4(1,2,3);  
}  
```
