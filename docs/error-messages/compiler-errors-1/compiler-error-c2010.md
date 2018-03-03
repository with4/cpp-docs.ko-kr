---
title: "컴파일러 오류 C2010 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2010
dev_langs:
- C++
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7f06e02e3e566c8b01edd24d159b42c452113775
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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