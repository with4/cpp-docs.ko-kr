---
title: "컴파일러 오류 C2628 | Microsoft Docs"
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
  - "C2628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2628"
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' 다음에 'type2'이\(가\) 올 수 없습니다. ';'이 있어야 합니다.  
  
 세미콜론이 없는 것 같습니다.  
  
 다음 샘플에서는 C2628 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2628.cpp  
class CMyClass {}  
int main(){}   // C2628 error  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2628b.cpp  
class CMyClass {};  
int main(){}  
```