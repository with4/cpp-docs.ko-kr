---
title: "컴파일러 오류 C2033 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2033
dev_langs:
- C++
helpviewer_keywords:
- C2033
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ba0fcc5d0938c796c94e6201be18d6c1fb6158b0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2033"></a>컴파일러 오류 C2033
'identifier': 비트 필드에 간접 참조를 사용할 수 없습니다.  
  
 비트 필드가 허용되지 않는 포인터로 선언되었습니다.  
  
 다음 샘플에서는 C2033을 생성합니다.  
  
```  
// C2033.cpp  
struct S {  
   int *b : 1;  // C2033  
};  
```  
  
 해결 방법:  
  
```  
// C2033b.cpp  
// compile with: /c  
struct S {  
   int b : 1;  
};  
```
