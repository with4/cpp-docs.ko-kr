---
title: "operator&lt;(&lt;sample container&gt;) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::operator<"
  - "operator<"
  - "std.<"
  - "<"
  - "std.operator<"
  - "std::<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "< 연산자"
  - "< 연산자, 특정 개체 비교"
  - "연산자 <, valarrays"
  - "operator<, valarrays"
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator&lt;(&lt;sample container&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  This topic is in the Visual C\+\+ documentation as a nonfunctional example of containers used in the Standard C\+\+ Library.  For more information, see [STL Containers](../standard-library/stl-containers.md).  
  
 Overloads **operator\<** to compare two objects of template class [Container](../standard-library/sample-container-class.md).  
  
## 구문  
  
```  
  
   template<class Ty>  
bool operator<(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## 반환 값  
 Returns `lexicographical_compare`\(\_*Left*.  [begin](../standard-library/container-class-begin.md), \_*Left*.  [end](../standard-library/container-class-end.md), \_*Right***.begin**, \_*Right*.**end**\).  
  
## 참고 항목  
 [\<sample container\>](../standard-library/sample-container.md)