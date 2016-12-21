---
title: "식의 배열 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], 식"
  - "식[C++], 배열"
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 식의 배열
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

배열 형식의 식별자가 `sizeof`, address\-of\(**&**\) 또는 참조의 초기화 이외의 식에 나타나는 경우 첫 번째 배열 요소에 대한 포인터로 변환됩니다.  예를 들면 다음과 같습니다.  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 `psz` 포인터는 `szError1` 배열의 첫 번째 요소를 가리킵니다.  포인터와 달리 배열은 수정할 수 있는 l\-value가 아닙니다.  따라서 다음 대입은 올바르지 않습니다.  
  
```  
szError1 = psz;  
```  
  
## 참고 항목  
 [배열](../cpp/arrays-cpp.md)