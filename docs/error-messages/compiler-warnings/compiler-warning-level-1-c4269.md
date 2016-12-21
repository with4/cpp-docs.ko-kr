---
title: "컴파일러 경고 (수준 1) C4269 | Microsoft Docs"
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
  - "C4269"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4269"
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4269
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 컴파일러가 생성한 기본 생성자를 사용하여 초기화된 'const' 자동 데이터는 신뢰할 수 없는 결과를 생성합니다.  
  
 특수한 클래스의 **const** 자동 인스턴스는 컴파일러가 생성한 기본 생성자를 사용하여 초기화됩니다.  
  
## 예제  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 이 클래스 인스턴스가 스택에 생성되므로 어떤 값도 `m_data`의 초기 값이 될 수 있습니다.  또한 이 인스턴스는 **const**이므로 `m_data`의 값을 변경할 수 없습니다.