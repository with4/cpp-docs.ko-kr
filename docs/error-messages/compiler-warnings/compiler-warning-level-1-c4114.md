---
title: "컴파일러 경고 (수준 1) C4114 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4114
dev_langs: C++
helpviewer_keywords: C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b2c75e8222655404dbda9fdc751c57fdf4982a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4114"></a>컴파일러 경고 (수준 1) C4114
동일한 형식 한정자를 두 번 이상 사용했습니다.  
  
 형식 한정자를 사용 하 여 형식 선언 또는 정의 (**const**, `volatile`, **서명**, 또는 `unsigned`) 두 번 이상. 이렇게 하면 경고 이며 Microsoft 확장명 (/Ze)와 ANSI 호환성 (/Za)에서 오류를 발생 합니다.  
  
 다음 샘플에서는 C4114 오류가 생성 됩니다.  
  
```  
// C4114.cpp  
// compile with: /W1 /c  
volatile volatile int i;   // C4114  
```  
  
 다음 샘플에서는 C4114 오류가 생성 됩니다.  
  
```  
// C4114_b.cpp  
// compile with: /W1 /c  
static const int const * ii;   // C4114  
static const int * const iii;   // OK  
```