---
title: "Compiler Error C3209 | Microsoft Docs"
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
  - "C3209"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3209"
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3209
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 제네릭 클래스는 관리되는 또는 WinRT 클래스여야 합니다.  
  
 제네릭 클래스는 관리되는 클래스 또는 Windows 런타임 클래스여야 합니다.  
  
 다음 샘플에서는 C3209를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3209.cpp  
// compile with: /clr  
generic <class T>  
class C {};   // C3209  
  
// OK - ref class can be generic  
generic <class T>  
ref class D {};  
```