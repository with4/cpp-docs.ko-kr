---
title: "범위 읽기 | Microsoft Docs"
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
  - "C"
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 범위 읽기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.9.6.2** `fscanf` 함수에서 % \[ 변환을 위한 scanlist의 첫 번째 문자도 아니고 마지막 문자도 아닌 대시\(–\) 문자의 해석  
  
 다음 줄  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 에서는 A–Z 범위에 속한 문자의 개수를 `strptr`이 가리키는 문자열로 읽습니다.  
  
## 참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)