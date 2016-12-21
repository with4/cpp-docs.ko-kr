---
title: "marshal_context::~marshal_context | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context::~marshal_context"
  - "msclr.interop.marshal_context.~marshal_context"
  - "marshal_context.~marshal_context"
  - "msclr::interop::marshal_context::~marshal_context"
  - "~marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context 클래스[C++], 작업"
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context::~marshal_context
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`marshal_context` 개체를 소멸시킵니다.  
  
## 구문  
  
```  
~marshal_context();  
```  
  
## 설명  
 Some data conversions require a marshal context.  See [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md) for more information about which translations require a context and which marshaling file has to be included in your application.  
  
 Deleting a `marshal_context` object will invalidate the data converted by that context.  If you want to preserve your data after a `marshal_context` object is destroyed, you must manually copy the data to a variable that will persist.  
  
## 요구 사항  
 **헤더 파일:**\<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\>, 또는 \<msclr\\marshal\_atl.h \>  
  
 **네임 스페이스:** msclr::interop  
  
## 참고 항목  
 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context 클래스](../dotnet/marshal-context-class.md)