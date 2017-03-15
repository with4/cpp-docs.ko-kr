---
title: "Compiler Error C3099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3099"
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compiler Error C3099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword': 관리되는 특성에 대해 \[System::AttributeUsageAttribute\]를 사용하고, WinRT 특성에 대해 \[Windows::Foundation::Metadata::AttributeUsageAttribute\]를 사용합니다.  
  
 <xref:System.AttributeUsageAttribute>를 사용하여 **\/clr** 특성을 선언합니다.  `Windows::Foundation::Metadata::AttributeUsageAttribute`를 사용하여 Windows 런타임 특성을 선언합니다.  
  
 \/CLR 특성에 대한 자세한 내용은 [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.  Windows 런타임의 지원되는 특성에 대해서는 [Windows.Foundation.Metadata 네임스페이스](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3099 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```