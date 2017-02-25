---
title: "컴파일러 경고 (수준 4) C4202 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4202"
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : '...': 이름 목록의 프로토타입 매개 변수가 잘못되었습니다.  
  
 이전 스타일의 함수 정의에 가변 인수가 들어 있습니다.  이러한 정의는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 오류를 발생시킵니다.  
  
## 예제  
  
```  
// C4202.c  
// compile with: /W4  
void func( a, b, ...)   // C4202  
int a, b;  
{}  
  
int main()  
{  
}  
```