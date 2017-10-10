---
title: "컴파일러 오류 C2846 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2846
dev_langs:
- C++
helpviewer_keywords:
- C2846
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e7b25736f54218d06030fdb548a60b3c6850061e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2846"></a>컴파일러 오류 C2846
'constructor': 인터페이스는 생성자를 사용할 수 없습니다  
  
 Visual c + + [인터페이스](../../cpp/interface.md) 생성자를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2846 오류가 생성 됩니다.  
  
```  
// C2846.cpp  
// compile with: /c  
__interface C {  
   C();   // C2846 constructor not allowed in an interface  
};  
```
