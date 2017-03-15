---
title: "컴파일러 오류 C3857 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3857"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3857"
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3857
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 여러 개의 type 매개 변수 목록을 사용할 수 없습니다.  
  
 같은 형식에 여러 개의 템플릿 또는 제네릭이 지정되었습니다. 이는 허용되지 않습니다.  
  
 다음 샘플에서는 C3857 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3857.cpp  
template <class T, class TT>  
template <class T2>    // C3857  
struct B {};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3857b.cpp  
// compile with: /c  
template <class T, class TT, class T2>   
struct B {};  
```  
  
 제네릭을 사용하는 경우에도 C3857이 발생할 수 있습니다.  
  
```  
// C3857c.cpp  
// compile with: /clr  
generic <typename T>  
generic <typename U>  
ref class GC;   // C3857  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3857d.cpp  
// compile with: /clr /c  
generic <typename U>  
ref class GC;  
```