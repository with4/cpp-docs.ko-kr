---
title: "컴파일러 오류 C2514 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2514
dev_langs:
- C++
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f91dfffe27127cfbff20d7b2e67d097b65cae358
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2514"></a>컴파일러 오류 C2514
'class': 클래스에 생성자가 없습니다  
  
 클래스, 구조체 또는 공용 생성자를 없는 인스턴스화해야 하는 데 사용 되는 매개 변수와 일치 하는 매개 변수 목록 사용 합니다.  
  
 클래스는 인스턴스화할 수 전에 완벽 하 게 선언 되어야 합니다.  
  
 다음 샘플에서는 C2514 오류가 생성 됩니다.  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```
