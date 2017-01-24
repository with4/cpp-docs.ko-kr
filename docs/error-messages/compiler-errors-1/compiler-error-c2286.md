---
title: "컴파일러 오류 C2286 | Microsoft Docs"
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
  - "C2286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2286"
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier'의 멤버에 대한 포인터 표현이 이미 '상속'\(으\)로 설정되었습니다. 선언이 무시됩니다.  
  
 클래스에 대해 서로 다른 두 가지 pointer\-to\-member 표현이 존재합니다.  
  
 자세한 내용은 [상속 키워드](../../cpp/inheritance-keywords.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2286 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2286.cpp  
// compile with: /c  
class __single_inheritance X;  
class __multiple_inheritance X;   // C2286  
class  __multiple_inheritance Y;   // OK  
```