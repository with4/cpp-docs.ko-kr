---
title: "컴파일러 오류 C2004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2004
dev_langs:
- C++
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
caps.latest.revision: 10
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
ms.openlocfilehash: 81b2693ba3a1132738b5a1ff0e830fc4cef36e13
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2004"></a>컴파일러 오류 C2004
'defined(id)'가 필요합니다.  
  
 식별자는 전처리기 키워드 뒤의 괄호에 나타나야 합니다.  
  
 이 오류는 Visual Studio .NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로 생성될 수도 있습니다. 전처리기 지시문에 괄호가 없습니다. 전처리기 지시문에 닫는 괄호가 없는 경우 컴파일러에서 오류를 생성합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2004를 생성합니다.  
  
```  
// C2004.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG   // C2004  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```  
  
## <a name="example"></a>예제  
 해결 방법:  
  
```  
// C2004b.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG)  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```
