---
title: "컴파일러 오류 C3289 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3289
dev_langs:
- C++
helpviewer_keywords:
- C3289
ms.assetid: 3c1c623b-7fcf-43ab-a89a-8722532a8d29
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 28e79ec1da42e2dab150a0b89cd8bc4d7ff87180
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3289"></a>컴파일러 오류 C3289
'property': trivial 속성은 인덱싱할 수 없습니다.  
  
 속성이 잘못 선언되었습니다. 인덱싱된 속성에 대해 접근자를 정의해야 합니다. 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md) 를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3289를 생성합니다.  
  
```  
// C3289.cpp  
// compile with: /clr  
public ref struct C {  
   // user-defined simple indexer  
   property int indexer1[int];   // C3289  
  
   // user-defined indexer  
   property int indexer2[int] {  
      int get(int i) { return 0; }  
      void set(int i, int j) {}  
   }  
};  
  
int main() {  
   C ^ MyC = gcnew C();  
   MyC->indexer2[0] = 1;  
}  
```
