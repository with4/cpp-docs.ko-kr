---
title: "컴파일러 경고 (수준 4) C4673 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4673"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4673"
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4673
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier'을\(를\) Throw하면 다음 형식이 Catch 쪽에서 고려되지 않습니다.  
  
 throw 개체는 **catch** 블록에서 처리할 수 없습니다.  이 경고 다음 줄에 처리할 수 없는 각 형식이 오류 출력 목록으로 작성되고  처리할 수 없는 각 형식에 각각의 경고가 포함되어 있습니다.  자세한 내용은 각 특정 형식에 대한 경고를 참조하십시오.  
  
 다음 샘플에서는 C4673 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4673.cpp  
// compile with: /EHsc /W4  
class Base {  
private:  
   char * m_chr;  
public:  
   Base() {  
      m_chr = 0;  
   }  
  
   ~Base() {  
      if(m_chr)  
         delete m_chr;  
   }  
};  
  
class Derv : private Base {  
public:  
   Derv() {}  
   ~Derv() {}  
};  
  
int main() {  
   try {  
      Derv D1;  
      // delete previous line, uncomment the next line to resolve  
      // Base D1;  
      throw D1;   // C4673  
   }  
  
   catch(...) {}  
}  
```