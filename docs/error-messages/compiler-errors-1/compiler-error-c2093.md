---
title: 컴파일러 오류 C2093 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2093
dev_langs:
- C++
helpviewer_keywords:
- C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11419a7df335bd87077759228be1256c92d09caa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170715"
---
# <a name="compiler-error-c2093"></a>컴파일러 오류 C2093
'variable1': 'variable2' 자동 변수의 주소를 사용 하 여 초기화할 수 없습니다.  
  
 로 컴파일할 때 [/Za](../../build/reference/za-ze-disable-language-extensions.md), 프로그램 이니셜라이저로 자동 변수의 주소를 사용 하려고 합니다.  
  
 다음 샘플에서는 C2093 오류가 생성 됩니다.  
  
```  
// C2093.c  
// compile with: /Za /c  
void func() {  
   int li;   // an implicit auto variable  
   int * s[]= { &li };   // C2093 address is not a constant  
  
   // OK  
   static int li2;  
   int * s2[]= { &li2 };  
}  
```