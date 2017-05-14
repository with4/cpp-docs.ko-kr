---
title: "컴파일러 오류 C2178 | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 96232cdb52fc84a90c768fa23b8a98da913c7982
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

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

