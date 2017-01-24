---
title: "컴파일러 경고 (수준 2) C4094 | Microsoft Docs"
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
  - "C4094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4094"
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

태그 없는 'token'에서 기호를 선언하지 않았습니다.  
  
 컴파일러가 태그 없는 구조체, 공용 구조체 또는 클래스를 사용하여 빈 선언을 검색했으므로  이 선언은 무시됩니다.  
  
## 예제  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 이 조건은 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서 오류를 발생시킵니다.