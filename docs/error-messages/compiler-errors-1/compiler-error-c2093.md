---
title: "컴파일러 오류 C2093 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2093
dev_langs: C++
helpviewer_keywords: C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 329c5250067c1d7db275326c6a3debb73d389cf6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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