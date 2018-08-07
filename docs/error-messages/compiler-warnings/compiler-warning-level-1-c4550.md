---
title: 컴파일러 경고 (수준 1) C4550 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4550
dev_langs:
- C++
helpviewer_keywords:
- C4550
ms.assetid: f902b4ed-5f17-48ea-b693-92f4fb8c8054
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d08529006e54427e4327ce96666e551046c07e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276687"
---
# <a name="compiler-warning-level-1-c4550"></a>컴파일러 경고(수준 1) C4550
식이 인수 목록이 없는 함수로 계산  
  
 함수에 대 한 역참조 포인터에 인수 목록이 없습니다.  
  
## <a name="example"></a>예제  
  
```  
// C4550.cpp  
// compile with: /W1  
bool f()  
{  
   return true;  
}  
  
typedef bool (*pf_t)();  
  
int main()  
{  
   pf_t pf = f;  
   if (*pf) {}  // C4550  
   return 0;  
}  
```