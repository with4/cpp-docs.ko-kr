---
title: "컴파일러 오류 C3224 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3224
dev_langs:
- C++
helpviewer_keywords:
- C3224
ms.assetid: 129be22f-8f3e-4fc6-9ccd-d27d8ef91251
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 383d7a5d4eb77efeaaabbbd2e29c3618f9a7b582
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3224"></a>컴파일러 오류 C3224
'type': 'number'개의 제네릭 형식 인수를 사용하는 오버로드된 제네릭 클래스가 없습니다.  
  
 컴파일러가 적절한 오버로드를 찾지 못했습니다.  
  
 다음 샘플에서는 C3224를 생성합니다.  
  
```  
// C3224.cs  
// compile with: /target:library  
public class C<T> {}  
public class C<T,U> {}  
```  
  
 그리고  
  
```  
// C3224b.cpp  
// compile with: /clr  
#using "C3224.dll"  
int main() {  
   C<int,int,int>^ c = gcnew C<int,int,int>();   // C3224  
   C<int,int>^ c2 = gcnew C<int,int>();   // OK  
}  
```
