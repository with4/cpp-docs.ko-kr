---
title: "컴파일러 경고 C4430 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4430
dev_langs:
- C++
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36bf5954387f37ed9527051f900c54ff93da1c6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4430"></a>컴파일러 경고 C4430
형식 지정자가 없습니다. int로 가정합니다. 참고: c + + 기본 int를 지원 하지 않습니다.  
  
 이 오류는 Visual c + + 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다: 모든 선언 형식을; 명시적으로 지정 해야 int가 더 이상 사용 됩니다.  
  
 C4430은 항상 오류로 실행 됩니다.  와 함께이 경고를 해제할 수 있습니다는 `#pragma warning` 또는 **/wd**; 참조 [경고](../../preprocessor/warning.md) 또는 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, / we, /wo /Wv, /WX (경고 수준)](../../build/reference/compiler-option-warning-level.md)자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 c4430 오류가 발생 합니다.  
  
```  
// C4430.cpp  
// compile with: /c  
struct CMyClass {  
   CUndeclared m_myClass;  // C4430  
   int m_myClass;  // OK  
};  
  
typedef struct {  
   POINT();   // C4430  
   // try the following line instead  
   // int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```