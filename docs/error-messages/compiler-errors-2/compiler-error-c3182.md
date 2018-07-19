---
title: 컴파일러 오류 C3182 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3182
dev_langs:
- C++
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 503ad6d17b197392967681bfdf4e921aa21dc3e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254624"
---
# <a name="compiler-error-c3182"></a>컴파일러 오류 C3182
'class': using 선언 또는 액세스 선언 멤버 내에서 또는 관리 되는 WinRTtype 올바르지 않습니다.  
  
 A [를 사용 하 여](../../cpp/using-declaration.md) 선언은 모든 형식의 관리 되는 클래스 내에서 올바르지 않습니다.  
  
 다음 샘플에서는 C3182 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3182a.cpp  
// compile with: /clr /c  
ref struct B {  
   void mf(int) {  
   }  
};  
  
ref struct D : B {  
   using B::mf;   // C3182, delete to resolve  
   void mf(char) {  
   }  
};  
```  
