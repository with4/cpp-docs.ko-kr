---
title: "컴파일러 오류 C2757 | Microsoft Docs"
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
  - "C2757"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2757"
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2757
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : 이름이 같은 기호가 이미 있으므로 이 이름을 네임스페이스 이름으로 사용할 수 없습니다.  
  
 현재 컴파일에서 네임스페이스 식별자로 사용되는 기호가 참조된 어셈블리에서 이미 사용되고 있습니다.  
  
 다음 샘플에서는 C2757 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2757a.cpp  
// compile with: /clr /LD  
public ref class Nes {};  
```  
  
 두 번째 코드 파일:  
  
```  
// C2757b.cpp  
// compile with: /clr /c  
#using <C2757a.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public ref class X {};  
}  
```  
  
 다음 샘플에서는 C2757 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2757c.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
public __gc class Nes {};  
```  
  
 두 번째 코드 파일:  
  
```  
// C2757d.cpp  
// compile with: /clr:oldSyntax /c  
#using <C2757c.dll>  
#using <mscorlib.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public __gc class X {};  
}  
```