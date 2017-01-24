---
title: "컴파일러 오류 C2673 | Microsoft Docs"
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
  - "C2673"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2673"
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2673
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 전역 함수에는 'this' 포인터가 없습니다.  
  
 전역 함수에서 `this`에 액세스하려고 했습니다.  
  
 다음 샘플에서는 C2673 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2673.cpp  
int main() {  
   this = 0;   // C2673  
}  
```