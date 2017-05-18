---
title: "컴파일러 경고 (수준 3) C4823 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: 12
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
ms.openlocfilehash: ea03723f9ccae2348a47ae4894097f5cd9f8b5a1
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4823"></a>컴파일러 경고(수준 3) C4823
'function': 고정 포인터 되었지만 해제를 사용 하 여 의미 체계를 사용할 수 없습니다. /EHa를 사용 하는 것이 좋습니다.  
  
블록 범위에서 선언 하는 고정 포인터에 의해 관리 되는 힙에 있는 개체를 제거 하려면 컴파일러의 고정 포인터에 포인터를 무효화 하는 소멸자 "가장", 로컬 클래스의 소멸자는 동작이 시뮬레이션 합니다. 예외를 throw 한 후 소멸자에 대 한 호출을 사용 하려면 기능을 활성화 해야 개체 해제를 사용 하 여 할 수 있는 [/EHsc](../../build/reference/eh-exception-handling-model.md)합니다.  
  
수동으로 개체를 해제 하 고 경고를 무시 수 있습니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C4823 오류가 발생 합니다.  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  

