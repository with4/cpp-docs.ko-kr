---
title: "컴파일러 오류 C2087 | Microsoft Docs"
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
  - "C2087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2087"
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 첨자가 없습니다.  
  
 여러 첨자로 구성된 배열의 정의에 2차원 이상에 대한 첨자 값이 없습니다.  
  
 다음 샘플에서는 C2087 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2087.cpp  
int main() {  
   char a[10][];   // C2087  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2087b.cpp  
int main() {  
   char b[4][5];  
}  
```