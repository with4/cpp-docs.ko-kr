---
title: "컴파일러 경고 (수준 3) C4995 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4995
dev_langs:
- C++
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c8bf04670f8899209a42e2cc8d20420d522ef4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4995"></a>컴파일러 경고 (수준 3) C4995
'function': 이름 #pragma 사용 되지 않는 것으로 표시 되었습니다  
  
 컴파일러가 pragma로 표시 된 함수를 발견 했습니다. [사용 되지 않는](../../preprocessor/deprecated-c-cpp.md)합니다. 이 함수는 이후 릴리스에서 제공되지 않을 수 있습니다. 해제할 수 있습니다이 경고와는 [경고](../../preprocessor/warning.md) pragma (아래 예제).  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4995 오류가 생성 됩니다.  
  
```  
// C4995.cpp  
// compile with: /W3  
#include <stdio.h>  
  
// #pragma warning(disable : 4995)  
void func1(void)  
{  
    printf("\nIn func1");  
}  
  
int main()   
{  
    func1();  
    #pragma deprecated(func1)  
    func1();   // C4995  
}  
```