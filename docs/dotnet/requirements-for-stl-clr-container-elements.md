---
title: "STL/CLR 컨테이너 요소에 대한 요구 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨테이너, STL"
  - "컨테이너, STL/CLR"
  - "표준 C++ 라이브러리, 템플릿 클래스 컨테이너"
  - "STL/CLR, 컨테이너"
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# STL/CLR 컨테이너 요소에 대한 요구 사항
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

All reference types that are inserted into STL\/CLR containers must have, at a minimum, the following elements:  
  
-   A public copy constructor.  
  
-   A public assignment operator.  
  
-   A public destructor.  
  
 Furthermore, associative containers such as [set](../dotnet/set-stl-clr.md) and [map](../dotnet/map-stl-clr.md) must have a public comparison operator defined, which is `operator<` by default.  Some operations on containers might also require a public default constructor and a public equivalence operator to be defined.  
  
 Like reference types, value types and handles to reference types that are to be inserted into an associative container must have a comparison operator such as `operator<` defined.  The requirements for a public copy constructor, public assignment operator, and a public destructor do not exist for value types or handles to reference types.  
  
## 참고 항목  
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)