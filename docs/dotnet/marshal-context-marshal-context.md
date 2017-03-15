---
title: "marshal_context::marshal_context | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::interop::marshal_context::marshal_context"
  - "marshal_context::marshal_context"
  - "msclr.interop.marshal_context.marshal_context"
  - "marshal_context.marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context 클래스[C++], 작업"
ms.assetid: 5f08c895-60b0-4f72-97ff-7ae37c68e853
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# marshal_context::marshal_context
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Constructs a `marshal_context` object to use for data conversion between managed and native data types.  
  
## 구문  
  
```  
marshal_context();  
```  
  
## 설명  
 Some data conversions require a marshal context.  See [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md) for more information about which translations require a context and which marshaling file has to be included in your application.  
  
## 예제  
 [marshal\_context::marshal\_as](../dotnet/marshal-context-marshal-as.md)의 예제를 참조하십시오.  
  
## 요구 사항  
 **헤더 파일:**\<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\>, 또는 \<msclr\\marshal\_atl.h \>  
  
 **네임 스페이스:** msclr::interop  
  
## 참고 항목  
 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context 클래스](../dotnet/marshal-context-class.md)