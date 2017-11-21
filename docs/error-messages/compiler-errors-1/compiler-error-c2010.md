---
title: "컴파일러 오류 C2010 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2010
dev_langs: C++
helpviewer_keywords: C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0863e96dfc137cf262fe1aef977c83dc592b798c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2010"></a>컴파일러 오류 C2010
'character': 매크로 정식 매개 변수 목록에  
  
 매크로 정의의 정식 매개 변수 목록에서 문자가 잘못 사용되었습니다. 오류를 해결 하려면 해당 문자를 제거 합니다.  
  
 다음 샘플에서는 C2010 오류가 생성 됩니다.  
  
```  
// C2010.cpp  
// compile with: /c  
#define mymacro(a|) (2*a)   // C2010  
#define mymacro(a) (2*a)   // OK  
```