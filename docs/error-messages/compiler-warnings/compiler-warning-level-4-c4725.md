---
title: "컴파일러 경고 (수준 4) C4725 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4725
dev_langs: C++
helpviewer_keywords: C4725
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a8b687257c3c00d37104e4a4f900f7e1e4af8e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4725"></a>컴파일러 경고(수준 4) C4725
명령이 일부 Pentium에서 정확하지 않을 수 있습니다.  
  
 코드에 일부 Pentium 마이크로프로세서에서 정확한 결과를 생성하지 않을 수 있는 인라인 어셈블리 명령이 포함되어 있습니다.  
  
 다음 샘플에서는 C4725를 생성합니다.  
  
```  
// C4725.cpp  
// compile with: /W4  
// processor: x86  
double m32fp = 2.0003e-17;  
  
void f() {  
   __asm  
   {  
      FDIV m32fp   // C4725  
   }  
}  
  
int main() {  
}  
```