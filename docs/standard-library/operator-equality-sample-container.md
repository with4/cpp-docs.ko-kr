---
title: "operator==(&lt;sample container&gt;) | Microsoft Docs"
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
  - "std.=="
  - "std::=="
  - "operator=="
  - "std.operator=="
  - "std::operator=="
  - "=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "== 연산자, 특정 표준 C++ 개체와 사용"
  - "연산자 ==, 컨테이너"
  - "operator==, 컨테이너"
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator==(&lt;sample container&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  This topic is in the Visual C\+\+ documentation as a nonfunctional example of containers used in the Standard C\+\+ Library.  For more information, see [STL Containers](../standard-library/stl-containers.md).  
  
 Overloads `operator==` to compare two objects of template class [Container](../standard-library/sample-container-class.md).  
  
## 구문  
  
```  
  
   template<class Ty>  
bool operator==(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## 반환 값  
 Returns `_Left`**.**[size](../standard-library/container-class-size.md) **\=\=** `_Right`**.size && equal**\(\_*Left***.** [begin](../standard-library/container-class-begin.md), `_Left`.  [end](../standard-library/container-class-end.md)*, \_Right***.begin**\).  
  
## 참고 항목  
 [\<sample container\>](../standard-library/sample-container.md)