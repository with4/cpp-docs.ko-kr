---
title: "컴파일러 오류 C2523 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2523
dev_langs:
- C++
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d9ec6a9196498f210e680acf17efd34ac84faf77
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2523"></a>컴파일러 오류 C2523
' 클래스:: ~ identifier': 소멸자/종료자 태그 일치 하지 않습니다.  
  
 소멸자 이름은 클래스 이름 앞에 물결표 이어야 합니다 (`~`). 생성자와 소멸자는 클래스와 동일한 이름을 가진는 유일한 멤버입니다.  
  
 다음 샘플에서는 C2523 오류가 생성 됩니다.  
  
```  
// C2523.cpp  
// compile with: /c  
class A {  
   ~B();    // C2523  
   ~A();   // OK  
};  
```
