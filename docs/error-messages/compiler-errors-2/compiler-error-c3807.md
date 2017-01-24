---
title: "컴파일러 오류 C3807 | Microsoft Docs"
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
  - "C3807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3807"
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : ComImport 특성이 있는 클래스는 'type2'에서 파생될 수 없으며 인터페이스만 구현할 수 있습니다.  
  
 <xref:System.Runtime.InteropServices.ComImportAttribute>에서 파생된 형식에서는 인터페이스만 구현할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C3807 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3807.cpp  
// compile with: /clr /c  
ref struct S {};  
interface struct I {};  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 : S {};   // C3807  
ref struct S2 : I {};  
```