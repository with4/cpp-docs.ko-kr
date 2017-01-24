---
title: "컴파일러 경고 (수준 1) C4010 | Microsoft Docs"
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
  - "C4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4010"
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

한 줄로 된 주석에 줄 연속 문자가 있습니다.  
  
 \/\/로 시작되는 한 줄로 된 주석에는 줄 연속 문자의 역할을 수행하는 백슬래시\(\\\)가 들어 있습니다.  컴파일러는 백슬래시 다음에 오는 줄이 연속된다고 생각하여 주석으로 처리합니다.  
  
 일부 구문 지향 편집기는 연속 문자 다음에 오는 줄을 주석으로 표시하지 않습니다.  이 경고를 발생시키는 줄에 대한 구문 색은 무시하십시오.  
  
 다음 샘플에서는 C4010 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```