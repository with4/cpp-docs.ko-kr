---
title: "고유 클래스에 대해 &gt;&gt; 연산자 오버로드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연산자 >>, 사용자 고유의 클래스를 위한 오버로딩"
  - "연산자 >>"
  - "연산자 >>, 사용자 고유의 클래스를 위한 오버로딩"
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 고유 클래스에 대해 &gt;&gt; 연산자 오버로드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Input streams use the extraction \(`>>`\) operator for the standard types.  You can write similar extraction operators for your own types; your success depends on using white space precisely.  
  
 Here is an example of an extraction operator for the `Date` class presented earlier:  
  
```  
istream& operator>> ( istream& is, Date& dt )  
{  
   is >> dt.mo >> dt.da >> dt.yr;  
   return is;  
}  
```  
  
## 참고 항목  
 [Input Streams](../standard-library/input-streams.md)