---
title: "컴파일러 경고 (수준 1) C4377 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4377"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4377"
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4377
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

네이티브 형식은 기본적으로 private입니다. \-d1PrivateNativeTypes는 사용되지 않습니다.  
  
 이전 릴리스에서 어셈블리의 네이티브 형식은 기본적으로 public이었으며, 이들을 private으로 만들기 위해 문서화되지 않은 내부 컴파일러 옵션\(**\/d1PrivateNativeTypes**\)이 사용되었습니다.  
  
 이제 어셈블리의 모든 형식\(네이티브 및 CLR\)은 기본적으로 private이므로 **\/d1PrivateNativeTypes**는 더 이상 필요하지 않습니다.  
  
## 예제  
 다음 샘플에서는 C4377 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```