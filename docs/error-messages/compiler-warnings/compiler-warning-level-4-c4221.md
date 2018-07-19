---
title: 컴파일러 경고 (수준 4) C4221 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4221
dev_langs:
- C++
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e602eb662533207a1f2957d3b11a0823e4b83af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293197"
---
# <a name="compiler-warning-level-4-c4221"></a>컴파일러 경고(수준 4) C4221
비표준 확장이 사용 됨: 'identifier': 자동 변수의 주소를 사용 하 여 초기화할 수 없습니다.  
  
 기본 Microsoft 확장 (/Ze)을 사용 하면 집계 형식의 초기화할 수 있습니다 (**배열**, `struct`, 또는 **union**) 로컬 (자동) 변수의 주소를 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// C4221.c  
// compile with: /W4  
struct S  
{  
   int *i;  
};  
  
void func()  
{  
   int j;  
   struct S s1 = { &j };   // C4221  
}  
  
int main()  
{  
}  
```  
  
 이러한 초기화는 ANSI 규격 사용할 수 없습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).