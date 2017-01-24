---
title: "컴파일러 오류 C3813 | Microsoft Docs"
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
  - "C3813"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3813"
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

property 선언은 WinRT 또는 관리되는 형식의 정의 내에서만 사용할 수 있습니다.  
  
 [property](../../misc/property.md)는 Windows 런타임 또는 관리되는 형식 내에서만 선언할 수 있습니다.  네이티브 형식은 `property` 키워드를 지원하지 않습니다.  
  
 다음 샘플에서는 C3813 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```