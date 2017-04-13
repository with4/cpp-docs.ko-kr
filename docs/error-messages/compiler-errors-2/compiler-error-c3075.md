---
title: "컴파일러 오류 C3075 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3075
dev_langs:
- C++
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
caps.latest.revision: 5
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b94da321ec35c840d929fe3b17ebb63885d86994
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3075"></a>컴파일러 오류 C3075
'instance': 참조 형식 'type'의 인스턴스는 값 형식에 포함할 수 없습니다.  
  
 값 형식이 참조 형식의 인스턴스를 포함할 수 없습니다.  
  
 자세한 내용은 참조 [참조 형식에 대 한 c + + 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3075를 생성합니다.  
  
```  
// C3075.cpp  
// compile with: /clr /c  
ref struct U {};  
value struct X {  
   U y;   // C3075  
};  
  
ref struct Y {  
   U y;   // OK  
};  
```
