---
title: "컴파일러 오류 C3769 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3769
dev_langs:
- C++
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 097b12ca4cdca8f465fd5383e42609187b66d32e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3769"></a>컴파일러 오류 C3769
'type': 중첩 된 클래스에는 바로 바깥쪽 클래스와 동일한 이름을 가질 수 없습니다  
  
 중첩된 클래스 바로 바깥쪽의 클래스와 같은 이름을 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3769 오류가 발생 합니다.  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```
