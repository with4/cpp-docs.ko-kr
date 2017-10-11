---
title: "컴파일러 오류 C3891 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3891
dev_langs:
- C++
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b9db8f6142e4d2d99071d9d02255e0789a14dd50
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3891"></a>컴파일러 오류 C3891
'var': 리터럴 데이터 멤버는 l-value로 사용할 수 없습니다  
  
 A [리터럴](../../windows/literal-cpp-component-extensions.md) 변수는 const 및 선언에 초기화 한 후 해당 값을 변경할 수 없습니다.  
  
 다음 샘플에서는 C3891 오류가 생성 됩니다.  
  
```  
// C3891.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3891  
}  
```
