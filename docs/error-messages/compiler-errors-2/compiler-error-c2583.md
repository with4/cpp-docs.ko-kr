---
title: "컴파일러 오류 C2583 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2583
dev_langs:
- C++
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8199698332d74242ef2dff9e43e26835afc0311c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2583"></a>컴파일러 오류 C2583
'identifier': ' const/volatile ' 'this'이 포인터는 생성자/소멸자에 적합 하지 않습니다  
  
 생성자 또는 소멸자가 선언 된 `const` 또는 `volatile`합니다. 이것은 허용되지 않습니다.  
  
 다음 샘플에서는 C2583 오류가 생성 됩니다.  
  
```  
// C2583.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
   A() const;   // C2583  
  
   // try the following line instead  
   // A();  
};  
```