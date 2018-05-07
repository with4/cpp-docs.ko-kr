---
title: 컴파일러 오류 C3645 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3645
dev_langs:
- C++
helpviewer_keywords:
- C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a711f37e3ab54de5e3cfad77b82fbd603edfaf6e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3645"></a>컴파일러 오류 C3645
'function': __clrcall을 네이티브 코드로 컴파일된 함수에서 사용할 수 없습니다  
  
 함수에 일부 키워드의 존재 여부도 인해 네이티브로 컴파일하도록 함수 됩니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3645 오류가 발생 합니다.  
  
```  
// C3645.cpp  
// compile with: /clr /c  
#pragma unmanaged   
int __clrcall dog() {}   // C3645  
```