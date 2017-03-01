---
title: "컴파일러 오류 c&2712; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2712
dev_langs:
- C++
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
caps.latest.revision: 15
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 89b7d0ad3c7e175db1525c2f3fb8407240ce943c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2712"></a>컴파일러 오류 c&2712;
개체 해제 기능이 사용되는 함수에서는 __try를 사용할 수 없습니다.  
  
 오류 c&2712; 사용 하는 경우에 발생할 수 있습니다 [/EHsc](../../build/reference/eh-exception-handling-model.md), 구조적된 예외 처리도 사용 하는 함수에 해제 (소멸)를 필요로 하는 개체입니다.  
  
 가능한 해결 방법:  
  
-   SEH가 필요한 코드를 다른 함수로 이동합니다.  
  
-   SEH를 사용하는 함수를 다시 작성하여 소멸자가 있는 지역 변수 및 매개 변수를 사용하지 않도록 합니다. 생성자 또는 소멸자에 SEH를 사용하지 않습니다.  
  
-   /EHsc 없이 컴파일합니다.  
  
 사용 하 여 선언 된 메서드를 호출 하는 경우에 오류 c&2712; 발생할 수 있습니다는 [__event](../../cpp/event.md) 키워드입니다. 이 이벤트는 다중 스레드 환경에서 사용할 수 있으므로 컴파일러는 내부 이벤트 개체의 조작을 방지 한 다음 생성된 된 코드는 SEH를 코드를 생성 하는 [try-finally 문](../../cpp/try-finally-statement.md)합니다. 따라서 이벤트 메서드를 호출하고 해당 형식에 소멸자가 포함된 인수를 값으로 전달하는 경우 C2712 오류가 발생합니다. 이 경우 한 가지 해결 방법은 인수를 상수 참조로 전달하는 것입니다.  
  
## <a name="example"></a>예제  
 C&2712;는으로 컴파일하는 경우에 발생할 수 있습니다 **/clr: pure** 에서 함수에 대 한 포인터의 정적 배열을 선언 하는 `__try` 블록. 정적 멤버에 동적 초기화에서 사용 하도록 컴파일러에 필요 **/clr: pure**, c + + 예외 처리를 의미 있는 합니다. 그러나 C++ 예외 처리는 `__try` 블록에서 허용되지 않습니다.  
  
 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않습니다.  
  
 다음 샘플에서는 C2712 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2712.cpp  
// compile with: /clr:pure /c  
struct S1 {  
   static int smf();  
   void fnc();  
};  
  
void S1::fnc() {  
   __try {  
      static int (*array_1[])() = {smf,};   // C2712  
  
      // OK  
      static int (*array_2[2])();  
      array_2[0] = smf;  
    }  
    __except(0) {}  
}  
```
