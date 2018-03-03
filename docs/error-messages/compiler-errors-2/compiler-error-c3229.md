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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24911d0ccd78788e37379dd7757fe97785cdd5a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3229"></a>컴파일러 오류 C3229
'type': 제네릭 형식 매개 변수에 대한 간접 참조는 허용되지 않습니다.  
  
 `*`, `^`또는 `&`와 제네릭 매개 변수를 사용할 수 없습니다.  
  
## <a name="example"></a>예  
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
  
## <a name="example"></a>예  
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