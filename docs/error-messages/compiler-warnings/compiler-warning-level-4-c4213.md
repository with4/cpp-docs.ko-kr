---
title: 컴파일러 경고 (수준 4) C4213 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4213
dev_langs:
- C++
helpviewer_keywords:
- C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 407fac636ea33c8cbd31104460442e5ac2aaec65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302908"
---
# <a name="compiler-warning-level-4-c4213"></a>컴파일러 경고(수준 4) C4213
비표준 확장이 사용 됨: l-value를 캐스팅 합니다.  
  
 기본 Microsoft 확장 (/Ze) 대입문의 왼쪽에 캐스트를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// C4213.c  
// compile with: /W4  
void *a;  
void f()  
{  
   int   i[3];  
   a = &i;  
   *(( int * )a )++ = 3;  // C4213  
}  
  
int main()  
{  
}  
```  
  
 이러한 캐스트는 ANSI 규격 사용할 수 없습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).