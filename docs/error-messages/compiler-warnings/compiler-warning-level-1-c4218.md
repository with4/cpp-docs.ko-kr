---
title: 컴파일러 경고 (수준 1) C4218 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4218
dev_langs:
- C++
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88b27af84c390760274bb20665eec4452c8e7072
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279752"
---
# <a name="compiler-warning-level-1-c4218"></a>컴파일러 경고(수준 1) C4218
비표준 확장이 사용 됨: 저장소 클래스 또는 형식을 지정 해야 합니다  
  
 기본 Microsoft 확장 (/Ze) 형식이 나 저장소 클래스를 지정 하지 않고 변수를 선언할 수 있습니다. 기본 형식은 `int`입니다.  
  
## <a name="example"></a>예제  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 이러한 선언이 ANSI 규격 올바르지 않습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).