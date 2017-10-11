---
title: "컴파일러 오류 C2892 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2892
dev_langs:
- C++
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 821069a21b6cf935590e0c999c5dbda1c69801f2
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2892"></a>컴파일러 오류 C2892
지역 클래스 멤버 템플릿을 가질 수 없습니다.  
  
 템플릿 멤버 함수는 함수에 정의 된 클래스에서 유효 하지 않습니다.  
  
 다음 샘플에서는 C2892 오류가 생성 됩니다.  
  
```  
// C2892.cpp  
int main() {  
   struct local {  
      template<class T>   // C2892  
      void f() {}  
   };  
}  
```
