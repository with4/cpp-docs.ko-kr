---
title: "컴파일러 오류 C2494 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2494
dev_langs: C++
helpviewer_keywords: C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 11a8e6ebbca57a9e60e3348363d843f86a4e200b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2494"></a>컴파일러 오류 C2494
'keyword' 필터 식 내에서 호출할 수 없습니다 또는 __finally/finally 블록  
  
 사용할 수 없는 `keyword` 에 `__finally` 또는 finally 블록입니다.  
  
 다음 샘플에서는 C2494 오류가 생성 됩니다.  
  
```  
// C2494.cpp  
#include <malloc.h>  
  
int main() {  
   __try {}  
   __except ( _alloca(100), 1 ) {}   // C2494  
   __try {}  
   __finally {  
      _alloca(100);   // C2494  
   }  
}  
```  
  
 사용 하는 경우에 C2494 발생할 수 있습니다 **/clr**합니다.  
  
```  
// C2494b.cpp  
// compile with: /clr  
#include <malloc.h>  
  
int main() {  
   char * buf;  
   try {}  
   catch (char * buf2) {}  
   finally {  
      _alloca(100);   // C2494  
   }  
}  
```