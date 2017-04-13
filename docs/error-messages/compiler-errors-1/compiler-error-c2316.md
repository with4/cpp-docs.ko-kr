---
title: "컴파일러 오류 C2316 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fd99248bdfca428b01921e80eb902d482c0e95be
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2316"></a>컴파일러 오류 C2316
'exception' : 소멸자로 Catch할 수 없거나 복사 생성자에 액세스할 수 없습니다.  
  
 값별 또는 참조별 예외가 catch되었지만 복사 생성자 및/또는 대입 연산자에 액세스할 수 없습니다.  
  
 이전 버전의 컴파일러에서는 이 코드를 사용할 수 있었지만 이제 오류가 발생합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2316을 생성합니다.  
  
```  
// C2316.cpp  
// compile with: /EHsc  
#include <stdio.h>  
  
extern "C" int printf_s(const char*, ...);  
  
struct B   
{  
public:  
    B() {}  
    // Delete the following line to resolve.  
private:  
    // copy constructor  
    B(const B&)   
    {  
    }  
};  
  
void f(const B&)   
{  
}  
  
int main()   
{  
    try   
    {  
        B aB;  
        f(aB);  
    }  
    catch (B b) {   // C2316  
        printf_s("Caught an exception!\n");     
    }  
}  
```
