---
title: 심각한 오류 C1094 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1094
dev_langs:
- C++
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e227cbfaf46eb7616ae63eda02816e7d274ab85b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1094"></a>심각한 오류 C1094
'-Zmval1': 명령줄 옵션이 미리 컴파일된 헤더를 작성 하는 데 사용 되는 값과 일치 하지 않습니다 ('-Zmval2')  
  
 에 전달 되는 값 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 에 전달 되는 값과 동일한 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (**/Zm** 사용 하거나 만들 미리 컴파일된 동일 하는 모든 컴파일에서 같은 값 이어야 합니다 헤더 파일)입니다.  
  
 다음 샘플에서는 C1094 오류가 생성 됩니다.  
  
```  
// C1094.h  
int func1();  
```  
  
 그리고  
  
```  
// C1094.cpp  
// compile with: /Yc"C1094.h" /Zm200  
int u;  
int main() {  
   int sd = 32;  
}  
#include "C1094.h"  
```  
  
 그리고  
  
```  
// C1094b.cpp  
// compile with: /Yu"C1094.h" /Zm300 /c  
#include "C1094.h"   // C1094 compile with /Zm200  
void Test() {}  
```