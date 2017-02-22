---
title: "컴파일러 오류 C2868 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2868"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2868"
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C2868
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : using 선언의 구문이 잘못되었습니다. 정규화된 이름이 필요합니다.  
  
 [using 선언](../../cpp/using-declaration.md)에는 [정규화된 이름](http://msdn.microsoft.com/ko-kr/3fefb16d-8120-4627-8b3f-3d90fbdcd1df)이 필요합니다.  
  
 다음 샘플에서는 C2868 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2868.cpp  
class X {  
public:  
   int i;  
};  
  
class Y : X {  
public:  
   using X::i;   // OK  
};  
  
int main() {  
   using X;   // C2868  
}  
```