---
title: "컴파일러 오류 C3625 | Microsoft Docs"
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
  - "C3625"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3625"
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3625
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'native\_type': 네이티브 형식은 WinRT 또는 관리되는 형식 'type'에서 파생될 수 없습니다.  
  
 네이티브 클래스는 WinRT 또는 관리되는 클래스에서 상속할 수 없습니다.  자세한 내용은 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)를 참조하세요.  
  
 다음 샘플에서는 C3625 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3625.cpp  
// compile with: /clr /c  
ref class B {};  
class D : public B {};   // C3625 cannot inherit from a managed class  
```  
  
 다음 샘플에서는 C3625 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3625_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class B {};  
class D : public B {};   // C3625  cannot inherit from a managed class  
```