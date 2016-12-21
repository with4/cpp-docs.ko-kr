---
title: "컴파일러 오류 C3370 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3370"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3370"
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3370
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'idl\_module name': idl\_module이 아직 정의되지 않았습니다.  
  
 [idl\_module](../../windows/idl-module.md)을 사용하여 DLL의 진입점을 지정하려면 먼저 `idl_module`를 사용하여 DLL 이름을 지정해야 합니다.  
  
 다음 샘플에서는 C3370을 생성합니다.  
  
```  
// C3370.cpp [module(name=MyLibrary)]; // uncomment the following line to resolve the error // [idl_module(name="name1", dllname=x.dll)]; [idl_module(name="name1"), entry(100)] // C3370 int f1(); int main() { }  
```