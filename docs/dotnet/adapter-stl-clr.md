---
title: "adapter(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/adapter>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<adapter> 헤더[STL/CLR]"
  - "<cliext/adapter> 헤더[STL/CLR]"
  - "어댑터[STL/CLR]"
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# adapter(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The STL\/CLR header `<cliext/adapter>` specifies two template classes \(`collection_adapter` and `range_adapter`\), and the template function `make_collection`.  
  
## 구문  
  
```  
#include <cliext/adapter>  
```  
  
## 설명  
  
|클래스|설명|  
|---------|--------|  
|[collection\_adapter](../dotnet/collection-adapter-stl-clr.md)|Wraps the Base Class Library \(BCL\) collection as a range.|  
|[range\_adapter](../dotnet/range-adapter-stl-clr.md)|Wraps the range as a BCL collection.|  
  
|Function|설명|  
|--------------|--------|  
|[make\_collection](../dotnet/make-collection-stl-clr.md)|Creates a range adapter using an iterator pair.|  
  
## 요구 사항  
 **Header:** \<cliext\/adapter\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)