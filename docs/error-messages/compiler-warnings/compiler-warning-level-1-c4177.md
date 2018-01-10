---
title: "컴파일러 경고 (수준 1) C4177 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4177
dev_langs: C++
helpviewer_keywords: C4177
ms.assetid: 2b05a5b3-696e-4f21-818e-227b9335e748
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a0cfe64a25c4813a726b539cef2ce37533a9a2ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4177"></a>컴파일러 경고(수준 1) C4177
\#pragma pragma 전역 범위에 있어야 합니다.  
  
 [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) pragma는 로컬 범위 내에서 사용할 수 없습니다. **pragma** 는 전역 범위가 현재 범위 다음에 나올 때까지 유효하지 않습니다.  
  
 다음 샘플에서는 C4177을 생성합니다.  
  
```  
// C4177.cpp  
// compile with: /W1  
// #pragma bss_seg("global")   // OK  
  
int main() {  
   #pragma bss_seg("local")    // C4177  
}  
```