---
title: "컴파일러 오류 C3624 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3624"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3624"
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3624
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 이 형식을 사용하려면 어셈블리 'assembly'에 대한 참조가 있어야 합니다.  
  
 코드를 컴파일하는 데 필요한 어셈블리\(참조\)가 지정되지 않았습니다. 어셈블리를 [\#using](../../preprocessor/hash-using-directive-cpp.md) 지시문에 전달하십시오.  
  
 다음 샘플에서는 C3624 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3624.cpp  
// compile with: /clr /c  
#using <System.Windows.Forms.dll>  
  
// Uncomment the following 2 lines to resolve.  
// #using <System.dll>  
// #using <System.Drawing.dll>  
  
using namespace System;  
  
public ref class MyForm : public Windows::Forms::Form {};   // C3624  
```  
  
 다음 샘플에서는 C3624 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3624_b.cpp  
// compile with: /clr:oldSyntax /c  
#using <System.Windows.Forms.dll>  
  
// Uncomment the following 2 lines to resolve.  
// #using <System.dll>  
// #using <System.Drawing.dll>  
  
using namespace System;  
  
public __gc class MyForm : public Windows::Forms::Form {};   // C3624  
```