---
title: "컴파일러 오류 C3834 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3834
dev_langs:
- C++
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
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
ms.openlocfilehash: 2175483609a4c05cba7b02a2cd1693dd763e150e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3834"></a>컴파일러 오류 C3834
고정 포인터로 명시적으로 잘못 캐스팅했습니다. 대신 고정된 지역 변수를 사용하십시오.  
  
 고정 된 포인터에는 명시적 캐스팅이 허용 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3834 오류가 발생 합니다.  
  
```  
// C3834.cpp  
// compile with: /clr  
int main() {  
   int x = 33;  
  
   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834  
   pin_ptr<int> p2 = &x;   // OK  
}  
```  

