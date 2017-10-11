---
title: "컴파일러 오류 C3298 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3298
dev_langs:
- C++
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a21b2d28120cb5e1c936b632d67ff28bb6568210
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3298"></a>컴파일러 오류 C3298
'constraint_1': 'constraint_2'에 ref 제약 조건이 있고 'constraint_1'에 값 제약 조건이 있으므로 'constraint_2'를 제약 조건으로 사용할 수 없습니다.  
  
 제약 조건에 대해 함께 사용할 수 없는 특성을 지정할 수 없습니다. 예를 들어 제네릭 형식 매개 변수를 값 형식과 참조 형식 둘 다로 제한할 수 없습니다.  
  
 자세한 내용은 참조 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + /cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3298을 생성합니다.  
  
```  
// C3298.cpp  
// compile with: /clr /c   
generic<class T, class U>  
where T : ref class  
where U : T, value class   // C3298  
public ref struct R {};  
```
