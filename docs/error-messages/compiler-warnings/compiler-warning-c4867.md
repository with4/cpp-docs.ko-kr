---
title: "컴파일러 경고 C4867 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4867
dev_langs:
- C++
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
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
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 86437fca7bfeef662bef9fe8311fb746a661264d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4867"></a>컴파일러 경고 C4867
'function': 함수 호출 인수 목록이 없습니다. '호출'을 사용 하 여 멤버에 대 한 포인터를 만들려면  
  
 멤버 함수에 대 한 포인터를 잘못 초기화 되었습니다.  
  
 이 경고는 Visual c + + 2005에 대해 수행 된 컴파일러 규칙의 결과로 발생할 수 있습니다: 멤버 포인터 규칙이 향상 되었습니다.  Visual c + + 2005 이전에 컴파일된 코드를 생성할 c 4867이 발생 합니다.  
  
 이 경고는 항상 오류로 발생 합니다. 사용 하는 [경고](../../preprocessor/warning.md) pragma를 사용 하지 않도록이 경고를 설정 합니다. MFC/ATL 및 c&4867;이 발생 하는 방법에 대 한 자세한 내용은 참조 [_ATL_ENABLE_PTM_WARNING](http://msdn.microsoft.com/Library/00b9ff5c-9834-4c40-911e-ee88d512c4af)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c4867 오류가 발생 합니다.  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```
