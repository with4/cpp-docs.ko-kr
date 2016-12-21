---
title: "컴파일러 오류 C3838 | Microsoft Docs"
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
  - "C3838"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3838"
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3838
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type'을\(를\) 명시적으로 상속할 수 없습니다.  
  
 지정된 `type`은 어떠한 클래스에서도 기본 클래스 역할을 수행할 수 없습니다.  
  
 다음 샘플에서는 C3838 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3838a.cpp  
// compile with: /clr /c  
public ref class B : public System::Enum {};   // C3838  
```  
  
 다음 샘플에서는 C3838 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3838b.cpp  
// compile with: /clr:oldSyntax /c  
public __gc class B : public System::ValueType {};   // C3838  
```