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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9fbfb9a2302f306401ad6c824fda17303e47f5bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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