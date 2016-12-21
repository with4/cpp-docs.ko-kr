---
title: "컴파일러 경고 (수준 1) C4286 | Microsoft Docs"
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
  - "C4286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4286"
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' : 기본 클래스\('type2'\)에 의해 줄 number에서 catch되었습니다.  
  
 지정된 예외 형식은 이전 처리기에서 처리되었으며  두 번째 catch 형식은 첫 번째 형식에서 파생되었습니다.  기본 클래스에 대한 예외에서 파생 클래스에 대한 예외를 catch합니다.  
  
## 예제  
  
```  
//C4286.cpp  
// compile with: /W1  
#include <eh.h>  
class C {};  
class D : public  C {};  
int main()  
{  
    try  
    {  
        throw "ooops!";  
    }  
    catch( C ) {}  
    catch( D ) {}  // warning C4286, D is derived from C  
}  
```