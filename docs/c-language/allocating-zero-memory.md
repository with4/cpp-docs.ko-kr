---
title: "0 메모리 할당 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메모리 할당, 0 메모리"
  - "0 메모리"
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 0 메모리 할당
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.10.3** 요청된 크기가 0인 경우 `calloc`, `malloc` 또는 `realloc` 함수의 동작  
  
 `calloc`, `malloc` 및 `realloc` 함수는 0을 인수로 수락합니다.  실제 메모리가 할당되지는 않지만 유효한 포인터가 반환되고 이후에 realloc을 사용하여 메모리 블록을 수정할 수 있습니다.  
  
## 참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)