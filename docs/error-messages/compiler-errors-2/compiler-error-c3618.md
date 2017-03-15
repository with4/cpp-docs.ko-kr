---
title: "컴파일러 오류 C3618 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3618"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3618"
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3618
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': DLLImport로 표시된 메서드를 정의할 수 없습니다.  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>로 표시된 메서드는 지정된 .DLL에 정의됩니다.  
  
## 예제  
 다음 샘플에서는 C3618 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3618.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED   
void Func();   
  
void Func() {}   // C3618, remove this function definition to resolve  
```