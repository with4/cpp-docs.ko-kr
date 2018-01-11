---
title: "컴파일러 오류 C2009 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2009
dev_langs: C++
helpviewer_keywords: C2009
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c2d7e8efba4a1116d2d48e11a94d67161f3ca774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2009"></a>컴파일러 오류 C2009
매크로 형식 'identifier'를 다시 사용하세요.  
  
 매크로 정의의 형식 매개 변수 목록 식별자를 두 번 이상 사용합니다. 식별자 매크로 매개 변수 목록에서 고유 해야 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2009 오류가 생성 됩니다.  
  
```  
// C2009.cpp  
#include <stdio.h>  
  
#define macro1(a,a) (a*a)   // C2009  
  
int main()   
{  
    printf_s("%d\n", macro1(2));  
}  
```  
  
## <a name="example"></a>예  
 해결 방법:  
  
```  
// C2009b.cpp  
#include <stdio.h>  
  
#define macro2(a)   (a*a)   
#define macro3(a,b) (a*b)  
  
int main()   
{  
    printf_s("%d\n", macro2(2));  
    printf_s("%d\n", macro3(2,4));  
}  
```