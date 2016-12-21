---
title: "컴파일러 오류 C2874 | Microsoft Docs"
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
  - "C2874"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2874"
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2874
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

using 선언 때문에 'symbol'이\(가\) 여러 번 선언됩니다.  
  
 이 선언은 동일 항목을 두 번 정의합니다.  
  
 다음 샘플에서는 C2874 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2874.cpp  
namespace Z {  
   int i;  
}  
  
int main() {  
   int i;  
   using Z::i;   // C2874, i already declared  
}  
```