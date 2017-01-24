---
title: "auto_gcroot 클래스 | Microsoft Docs"
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
  - "msclr::auto_gcroot"
  - "msclr.auto_gcroot"
  - "auto_gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot"
ms.assetid: b5790912-265d-463e-a486-47302e91042a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Automatic resource management \(like [auto\_ptr 클래스](../standard-library/auto-ptr-class.md)\) which can be used to embed a virtual handle into a native type.  
  
## 구문  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### 매개 변수  
 `_element_type`  
 The managed type to be embedded.  
  
## 요구 사항  
 **Header file** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [auto\_gcroot](../dotnet/auto-gcroot.md)   
 [auto\_gcroot 멤버](../dotnet/auto-gcroot-members.md)   
 [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto\_handle 클래스](../dotnet/auto-handle-class.md)