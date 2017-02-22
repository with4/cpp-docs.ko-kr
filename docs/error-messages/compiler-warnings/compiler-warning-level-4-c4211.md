---
title: "컴파일러 경고 (수준 4) C4211 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4211"
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : extern에서 static으로 재정의되었습니다.  
  
 기본Microsoft 확장\(\/Ze\)을 사용하면 `extern` 식별자를 **static**으로 재정의할 수 있습니다.  
  
## 예제  
  
```  
// C4211.c  
// compile with: /W4  
extern int i;  
static int i;   // C4211  
  
int main()  
{  
}  
```  
  
 이러한 재정의는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 사용할 수 없습니다.  
  
## 참고 항목  
 [\(NOTINBUILD\)Static Storage\-Class Specifiers](http://msdn.microsoft.com/ko-kr/3ba9289a-a412-4a17-b319-ceb2c087df48)