---
title: "marshal_context 클래스 | Microsoft Docs"
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
  - "marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context 클래스[C++]"
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This class converts data between native and managed environments.  
  
## 구문  
  
```  
class marshal_context  
```  
  
## 설명  
 Use the `marshal_context` class for data conversions that require a context.  See [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md) for more information about which conversions require a context and which marshaling file has to be included.  The result of marshaling when you use a context is valid only until the `marshal_context` object is destroyed.  To preserve your result, you must copy the data.  
  
 The same `marshal_context` can be used for multiple data conversions.  Reusing the context in this manner will not affect the results from previous marshaling calls.  
  
## 요구 사항  
 **헤더 파일:**\<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\>, 또는 \<msclr\\marshal\_atl.h \>  
  
 **네임 스페이스:** msclr::interop  
  
## 참고 항목  
 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)