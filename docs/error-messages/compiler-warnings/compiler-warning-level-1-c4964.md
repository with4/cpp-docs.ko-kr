---
title: "컴파일러 경고 (수준 1) C4964 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4964"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4964"
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4964
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

최적화 옵션을 지정하지 않았으므로 프로필 정보가 수집되지 않습니다.  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) 및 [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)를 지정했지만 최적화를 요청하지 않았으므로 .pgc 파일이 생성되지 않고, 프로필 기반 최적화를 수행할 수 없습니다.  
  
 응용 프로그램을 실행할 때 .pgc 파일을 생성하려면 [\/O](../../build/reference/o-options-optimize-code.md) 컴파일러 옵션 중 하나를 지정해야 합니다.  
  
 다음 샘플에서는 C4964 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```