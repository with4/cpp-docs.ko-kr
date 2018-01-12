---
title: "컴파일러 경고 (수준 3) C4101 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4101
dev_langs: C++
helpviewer_keywords: C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 162ad70f6d87ba6de51f677d95f1af7c1b6d8054
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4101"></a>컴파일러 경고 (수준 3) C4101
'identifier': 참조 되지 않은 지역 변수  
  
 지역 변수 사용 되지 않습니다. 이 경고는 확실 한 경우에 발생 합니다.  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 그러나이 경고는도 발생를 호출할 때는 **정적** 멤버 함수가 클래스의 인스턴스를 통해:  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 이 경우 컴파일러에 대 한 정보를 사용 `si` 액세스로는 **정적** 함수가 있지만 클래스의 인스턴스를 호출 하는 데 필요 하지 않으므로 **정적** 함수; 따라서 경고 합니다. 이 경고를 해결 하려면 하면 다음과 같은 작업을 수행할 수 있습니다.  
  
-   컴파일러의 인스턴스를 사용 하는 생성자를 추가 `si` 에 대 한 호출에서 `func`합니다.  
  
-   제거는 **정적** 키워드의 정의를 `func`합니다.  
  
-   호출 된 **정적** 명시적으로 함수: `int y = S::func();`합니다.