---
title: "컴파일러 오류 C2348 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2348"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2348"
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2348
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type name' : C 스타일 집합체가 아니므로 포함 IDL에서 내보낼 수 없습니다.  
  
 [export](../../windows/export.md) 특성을 사용하여 .idl 파일에 `struct`를 배치하려면 `struct`에 데이터만 포함해야 합니다.  
  
 다음 샘플에서는 C2348 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2348.cpp  
// C2348 error expected  
[ module(name="SimpleMidlTest") ];  
  
[export]  
struct Point {  
   // Delete the following two lines to resolve.  
   Point() : m_i(0), m_j(0) {}  
   Point(int i, int j) : m_i(i), m_j(j) {}  
  
   int m_i;  
   int m_j;  
};  
```