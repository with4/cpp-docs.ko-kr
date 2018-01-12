---
title: "컴파일러 오류 C3182 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3182
dev_langs: C++
helpviewer_keywords: C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3485f017547e572b6090cabe9afb250c83b6fde3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
