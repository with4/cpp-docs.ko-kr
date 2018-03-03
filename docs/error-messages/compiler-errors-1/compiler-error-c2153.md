---
title: "컴파일러 오류 C2153 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2153
dev_langs:
- C++
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c766d2ef62f22bcdc61c23790d70fa3f09b490c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2153"></a>컴파일러 오류 C2153
16 진 상수에 16 진수가 적어도 하나 있어야 합니다.  
  
 16 진수 상수 x, X, 0 및 \x 올바르지 않습니다. 16 진수가 적어도 하나를 수행 해야 x 또는 X.  
  
 다음 샘플에서는 C2153 오류가 생성 됩니다.  
  
```  
// C2153.cpp  
int main() {  
   int a= 0x;    // C2153  
   int b= 0xA;   // OK  
}  
```