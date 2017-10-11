---
title: "컴파일러 오류 C3229 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3229
dev_langs:
- C++
helpviewer_keywords:
- C3229
ms.assetid: f2d90923-aa8b-444f-ab10-1f37dbb864e1
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4687643e69ff0c31f4aac9cd30c4fc307c8b02e4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3229"></a>컴파일러 오류 C3229
'type': 제네릭 형식 매개 변수에 대한 간접 참조는 허용되지 않습니다.  
  
 `*`, `^`또는 `&`와 제네릭 매개 변수를 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3229를 생성합니다.  
  
```  
// C3229.cpp  
// compile with: /clr /c  
generic <class T>  
ref class C {  
   T^ t;   // C3229  
};  
  
// OK  
generic <class T>  
ref class D {  
   T u;  
};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3229를 생성합니다.  
  
```  
// C3229_b.cpp  
// compile with: /clr /c  
generic <class T>   // OK  
ref class Utils {  
   static void sort(T elems[], size_t size);   // C3229  
   static void sort2(T elems, size_t size);   // OK  
};  
```
