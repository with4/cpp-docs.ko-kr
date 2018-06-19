---
title: 컴파일러 경고 (수준 4) C4205 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4205
dev_langs:
- C++
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc8c811fd8d67964bdef8149aea09d83e4649b99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292768"
---
# <a name="compiler-warning-level-4-c4205"></a>컴파일러 경고(수준 4) C4205
비표준 확장이 사용 됨: 함수 범위에 정적 함수 선언이  
  
 Microsoft 확장 (/Ze) **정적** 다른 함수 내 함수를 선언할 수 있습니다. 함수는 전역 범위를 지정 됩니다.  
  
## <a name="example"></a>예제  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 이러한 초기화는 ANSI 규격 사용할 수 없습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).