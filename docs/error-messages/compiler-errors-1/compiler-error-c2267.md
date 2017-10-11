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
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 42385c64119acfb669c7420ad9d3ba18d6daf60b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
