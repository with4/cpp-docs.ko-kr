---
title: "컴파일러 오류 C2473 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2473
dev_langs:
- C++
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bbc3432383e39913ed3cd89b310b00706a26a589
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2473"></a>컴파일러 오류 C2473
'identifier': 함수 정의로 보이지만 매개 변수 목록이 없습니다.  
  
 컴파일러가 매개 변수 목록 없이 함수처럼 보이는 항목을 발견했습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2473을 생성합니다.  
  
```  
// C2473.cpp  
// compile with: /clr /c  
class A {  
   int i {}   // C2473  
};  
  
class B {  
   int i() {}   // OK  
};  
```
