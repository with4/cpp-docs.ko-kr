---
title: "컴파일러 오류 C2178 | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: facb255b0c53a3de0e1d5c9f90de5835b25e3c32
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2178"></a>컴파일러 오류 C2178  
  
'*식별자*'로 선언할 수 없습니다'*지정자*' 지정자  
  
A `mutable` 지정자는 선언에서 사용 되었지만이 컨텍스트에서 지정자를 사용할 수 없습니다.  
  
`mutable` 지정자는 클래스 데이터 멤버의 이름에만 적용 될 수 있으며 이름 선언에 적용할 수 없습니다 `const` 또는 `static`, 참조 멤버에 적용할 수 없습니다.  
  
## <a name="example"></a>예제  
  
다음 샘플에서는 어떻게 C2178 발생할 수 있습니다, 그리고 및를 해결 하는 방법을 보여 줍니다.  
  
```  
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```  

