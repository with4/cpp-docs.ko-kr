---
title: 컴파일러 경고 (수준 3) C4101 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 973b966e4b589cb35ffc92da9031779b14d448e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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