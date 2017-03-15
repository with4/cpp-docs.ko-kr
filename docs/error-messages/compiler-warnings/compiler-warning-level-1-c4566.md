---
title: "컴파일러 경고 (수준 1) C4566 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4566"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4566"
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4566
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

유니버설 문자 이름 'char'\(으\)로 표현되는 문자는 현재 코드 페이지\(page\)에서 표현할 수 없습니다.  
  
 일부 유니코드 문자는 현재 ANSI 코드 페이지에서 표현할 수 없습니다.  
  
 좁은 문자열\(1바이트 문자\)은 멀티바이트 문자로 변환되는 반면 넓은 문자열\(2바이트 문자\)은 변환되지 않습니다.  
  
 다음 샘플에서는 C4566 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4566.cpp  
// compile with: /W1  
int main() {  
   char c1 = '\u03a0';   // C4566  
   char c2 = '\u0642';   // C4566  
  
   wchar_t c3 = L'\u03a0';   // OK  
   wchar_t c4 = L'\u0642';   // OK  
}  
```