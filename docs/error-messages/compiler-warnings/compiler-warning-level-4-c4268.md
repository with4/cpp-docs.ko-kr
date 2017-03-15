---
title: "컴파일러 경고 (수준 4) C4268 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4268"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4268"
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 4) C4268
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 컴파일러에서 생성한 기본 생성자를 사용하여 초기화된 'const' 정적\/전역 데이터는 개체를 0으로 채웁니다.  
  
 특수한 클래스의 **const** 전역 또는 정적 인스턴스는 컴파일러가 생성한 기본 생성자를 사용하여 초기화됩니다.  
  
## 예제  
  
```  
// C4268.cpp  
// compile with: /c /LD /W4  
class X {  
public:  
   int m_data;  
};  
  
const X x1;   // C4268  
```  
  
 이 클래스 인스턴스는 **const**이므로 `m_data` 값을 변경할 수 없습니다.