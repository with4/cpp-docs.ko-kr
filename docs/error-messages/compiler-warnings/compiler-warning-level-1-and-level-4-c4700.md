---
title: "컴파일러 경고(수준 1 및 수준 4) C4700 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4700"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4700"
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고(수준 1 및 수준 4) C4700
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

초기화되지 않은 'name' 지역 변수를 사용했습니다.  
  
 값을 할당하지 않은 *name* 지역 변수를 사용했으므로 예기치 않은 결과가 발생할 수 있습니다.  
  
 다음 샘플에서는 C4700 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md)가 지정된 경우 이 경고는 수준 4입니다.  다음 샘플에서는 C4700 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```