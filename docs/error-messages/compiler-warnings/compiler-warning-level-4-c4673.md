---
title: "컴파일러 경고 (수준 4) C4673 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4673
dev_langs: C++
helpviewer_keywords: C4673
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8242a083fbf7a9f94c419c1cf142c7c1ada65009
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4673"></a>컴파일러 경고(수준 4) C4673
'identifier' 다음 형식 발생 고려 되지 않습니다. catch 쪽에서  
  
 throw 개체를 처리할 수 없는 **catch** 블록입니다. 처리할 수 없는 각 유형에이 경고를 포함 하는 줄 바로 다음 오류 출력에 나열 됩니다. 처리 되지 않은 각 형식에는 자체 경고 합니다. 자세한 내용은 각 특정 형식에 대 한 경고를 읽습니다.  
  
 다음 샘플에서는 C4673 오류가 생성 됩니다.  
  
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