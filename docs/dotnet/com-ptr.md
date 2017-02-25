---
title: "com::ptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "com::ptr"
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# com::ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A wrapper for a COM object that can be used as a member of a CLR class.  The wrapper also automates lifetime management of the COM object, releasing owned references on the object when its destructor is called.  Analogous to [CComPtr Class](../atl/reference/ccomptr-class.md).  
  
## 구문  
  
```  
#include <msclr\com\ptr.h>  
```  
  
## 설명  
 [com::ptr 클래스](../dotnet/com-ptr-class.md) is defined in the \<msclr\\com\\ptr.h\> file.  
  
## 참고 항목  
 [C\+\+ 지원 라이브러리](../dotnet/cpp-support-library.md)