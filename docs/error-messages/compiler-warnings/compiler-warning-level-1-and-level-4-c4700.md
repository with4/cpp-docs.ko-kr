---
title: "컴파일러 경고 (수준 1 및 수준 4) C4700 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4700
dev_langs:
- C++
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f41e519a9dbcff3cc5ad4b718003e5964bfc3e85
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>컴파일러 경고(수준 1 및 수준 4) C4700
'name'가 사용 되는 초기화 되지 않은 지역 변수  
  
 지역 변수를 사용한 *이름* 예기치 않은 결과가 발생할 수 있는 값을 할당 하지 않고 있습니다.  
  
 다음 샘플에서는 C4700 오류가 생성 됩니다.  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 아래 [/clr: safe](../../build/reference/clr-common-language-runtime-compilation.md) 수준 4 경고입니다.  다음 샘플에서는 C4700 오류가 생성 됩니다.  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```
