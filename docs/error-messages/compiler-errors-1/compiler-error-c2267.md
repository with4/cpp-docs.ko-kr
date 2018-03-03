---
title: "컴파일러 오류 C2267 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2267
dev_langs:
- C++
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c7256335f096648eed0ffc9e15c3acb9f3c5ba1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2267"></a>컴파일러 오류 C2267
'function': 블록 범위가 있는 정적 함수를 사용할 수 없습니다.  
  
 로컬 함수를 선언 `static`합니다. 정적 함수는 전역 범위를 가져야 합니다.  
  
 다음 샘플에서는 C2267 오류가 생성 됩니다.  
  
```  
// C2267.cpp  
static int func2();   // OK  
int main() {  
    static int func1();   // C2267  
}  
```