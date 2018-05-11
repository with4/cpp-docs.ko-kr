---
title: 컴파일러 오류 C3890 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3890
dev_langs:
- C++
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc1bfbba9cfb8991491bcbb42d2e13c586c7fc26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3890"></a>컴파일러 오류 C3890
'var': 리터럴 데이터 멤버의 주소를 가져올 수 없습니다  
  
 가비지 수집 힙에 리터럴 데이터 멤버가 있습니다.  있으므로 주소 보다 유용한 경우가 가비지 수집 힙에 있는 개체를 이동할 수 있습니다.  
  
 다음 샘플에서는 C3890 오류가 생성 됩니다.  
  
```  
// C3890.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   int p = &Y1::staticConst;   // C3890  
   int p2 = Y1::staticConst;   // OK  
}  
```