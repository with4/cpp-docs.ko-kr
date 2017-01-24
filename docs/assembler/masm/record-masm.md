---
title: "RECORD (MASM) | Microsoft Docs"
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
  - "RECORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RECORD directive"
ms.assetid: c83db394-0fe3-468f-813f-13302cdc862d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# RECORD (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구성에 지정 된 필드가 있는 레코드 형식을 선언 합니다.  *fieldname* 의 필드 이름을 지정  *폭* 비트를 지정 및  *식* 해당 초기 값을 제공 합니다.  
  
## 구문  
  
```  
  
   recordname RECORD fieldname:width [[= expression]]   
[[, fieldname:width [[= expression]]]]...  
```  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)