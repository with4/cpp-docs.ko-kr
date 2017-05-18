---
title: "컴파일러 오류 C3609 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3609
dev_langs:
- C++
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ffb46df64ac0a18847c3595f9fb3fffc3bd26c51
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3609"></a>컴파일러 오류 C3609
'member': 봉인 함수 또는 최종 함수는 virtual이어야 합니다.  
  
 [봉인](../../windows/sealed-cpp-component-extensions.md) 및 [최종](../../cpp/final-specifier.md) 키워드는 표시 된 클래스, 구조체 또는 멤버 함수에만 사용할 수 `virtual`합니다.  
  
 다음 샘플에서는 C3609 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  

