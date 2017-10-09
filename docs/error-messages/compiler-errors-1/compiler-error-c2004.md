---
title: "컴파일러 오류 C2004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f4596e43fad713f6b0a81eea9e697c6e0f91c75b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
