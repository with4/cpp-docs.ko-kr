---
title: 컴파일러 오류 C3891 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3891
dev_langs:
- C++
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 021f19d50d0b83c9526956684737ad23fea9fb01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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