---
title: 컴파일러 오류 C2514 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2514
dev_langs:
- C++
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 255459a7ba9829b3db817662e2fc1139191b6385
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227977"
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