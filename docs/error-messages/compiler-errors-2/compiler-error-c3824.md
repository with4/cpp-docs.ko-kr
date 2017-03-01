---
title: "컴파일러 오류 C3824 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 546edbeccfee84e91018d0801f0c1ebc7a53a537
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3824"></a>컴파일러 오류 C3824
'member':이 형식은이 컨텍스트 (함수 매개 변수, 반환 형식 또는 정적 멤버)에 나타날 수 없습니다  
  
 고정 포인터는 함수 매개 변수, 반환 형식 안 또는 선언 된 `static`합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3824 오류가 생성 됩니다.  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  

