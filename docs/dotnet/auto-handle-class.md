---
title: "auto_handle 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_handle, msclr::auto_handle"
  - "msclr.auto_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle 클래스"
ms.assetid: a65604d1-ecbb-44fd-ae2f-696ddeeed9d6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# auto_handle 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Automatic resource management which can be used to embed a virtual handle into a managed type.  
  
## 구문  
  
```  
template<typename _element_type>  
ref class auto_handle;  
```  
  
#### 매개 변수  
 `_element_type`  
 The managed type to be embedded.  
  
## 요구 사항  
 **Header file** \<msclr\\auto\_handle.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [auto\_handle](../dotnet/auto-handle.md)   
 [auto\_handle 멤버](../dotnet/auto-handle-members.md)   
 [auto\_gcroot 클래스](../dotnet/auto-gcroot-class.md)