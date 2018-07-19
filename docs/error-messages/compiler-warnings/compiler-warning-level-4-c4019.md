---
title: 컴파일러 경고 (수준 4) C4019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4019
dev_langs:
- C++
helpviewer_keywords:
- C4019
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d015b5674ad8f64a68b86979ce93313fa098c867
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296509"
---
# <a name="compiler-warning-level-4-c4019"></a>컴파일러 경고(수준 4) C4019
전역 범위에 빈 문이 있습니다.  
  
 전역 범위의 세미콜론 앞에 문이 오지 않습니다.  
  
 불필요한 세미콜론을 제거하면 이 경고를 해결할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// C4019.c  
// compile with: /Za /W4  
#define declint( varname ) int varname;  
declint( a );   // C4019, int a;;  
declint( b )   // OK, int b;  
  
int main()  
{  
}  
```