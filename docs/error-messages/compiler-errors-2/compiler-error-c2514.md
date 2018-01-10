---
title: "컴파일러 오류 C2514 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2514
dev_langs: C++
helpviewer_keywords: C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58faaec5231b8d2d0629043e5e77139dc9e3386f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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