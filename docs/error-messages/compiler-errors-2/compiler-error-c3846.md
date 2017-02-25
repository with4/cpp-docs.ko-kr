---
title: "컴파일러 오류 C3846 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3846"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3846"
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3846
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 'assembly2'에서 기호를 가져올 수 없습니다. 'symbol'을\(를\) 다른 어셈블리 'assembly1'에서 이미 가져왔습니다.  
  
 기호를 참조된 어셈블리에서 이미 가져왔으므로 다른 참조된 어셈블리에서 가져올 수 없습니다.  
  
 다음 샘플에서는 C3846 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 그런 다음 아래 파일을 컴파일합니다.  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  
  
 다음 샘플에서는 C3846 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3846c.cpp  
// compile with: /LD /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __gc struct G  
{  
};  
```  
  
 그런 다음 아래 파일을 컴파일합니다.  
  
```  
// C3846d.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
#using "c3846c.dll"  
#using "c3846c.obj"   // C3846  
  
int main()  
{  
}  
```