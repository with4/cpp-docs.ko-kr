---
title: "링커 도구 오류 LNK1313 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1313"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1313"
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 오류 LNK1313
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ijw\/native 모듈이 발견되었습니다. 순수 모듈에 링크할 수 없습니다.  
  
 현재 Visual C\+\+ 버전에서는 네이티브 또는 혼합 관리\/네이티브 .obj 파일을 **\/clr:pure**로 컴파일된 .obj 파일에 링크할 수 없습니다.  
  
## 예제  
  
```  
// LNK1313.cpp  
// compile with: /c /clr:pure  
// a pure module  
int main() {}  
```  
  
## 예제  
  
```  
// LNK1313_b.cpp  
// compile with: /c /clr  
// an IJW module  
void test(){}  
```  
  
## 예제  
 다음 샘플에서는 LNK1313을 생성합니다.  
  
```  
// LNK1313_c.cpp  
// compile with: /link LNK1313.obj LNK1313_b.obj  
// LNK1313 warning expected  
```