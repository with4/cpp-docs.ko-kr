---
title: "컴파일러 오류 C3277 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3277
dev_langs:
- C++
helpviewer_keywords:
- C3277
ms.assetid: 8ac5f476-e30c-4879-92c6-f03cdbd74045
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c5ce51c198c998b96dfa941cb088276b610142f1
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3277"></a>컴파일러 오류 C3277
관리 되지 않는 열거형 'enum' 관리 되는 'type' 내부에 정의할 수 없습니다.  
  
 관리 되는 형식 내 열거형 잘못 정의 되었습니다.  
  
 다음 샘플에서는 C3277 오류가 생성 됩니다.  
  
```  
// C3277a.cpp  
// compile with: /clr  
ref class A  
{  
   enum E {e1,e2};   // C3277  
   // try the following line instead  
   // enum class E {e1,e2};  
};  
  
int main()  
{  
}  
```  

