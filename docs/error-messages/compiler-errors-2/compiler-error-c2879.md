---
title: "컴파일러 오류 C2879 | Microsoft Docs"
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
  - "C2879"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2879"
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2879
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : 네임스페이스 별칭 정의에 따라 기존 네임스페이스에만 다른 이름을 지정할 수 있습니다.  
  
 네임스페이스 이외의 기호에 대해 [네임스페이스 별칭](../../misc/namespace-alias.md)을 만들 수 없습니다.  
  
 다음 샘플에서는 C2879 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```