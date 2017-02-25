---
title: "심각한 오류 C1071 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1071"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1071"
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 심각한 오류 C1071
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

주석에서 예기치 않은 파일의 끝이 나타났습니다.  
  
 주석을 검색하는 동안 컴파일러가 파일의 끝에 도달했습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  주석 종결자\(\*\/\)가 없습니다.  
  
2.  소스 파일의 마지막 줄에서 주석 다음에 줄 바꿈 문자가 없습니다.  
  
 다음 샘플에서는 C1071 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C1071.cpp  
int main() {  
}  
  
/* this comment is fine */  
/* forgot the closing tag        // C1071  
```