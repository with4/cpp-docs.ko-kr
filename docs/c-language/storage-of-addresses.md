---
title: "주소 저장소 | Microsoft Docs"
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
  - "주소[C++], 저장소"
  - "저장소[C++], 주소"
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 주소 저장소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

주소에 필요한 저장소의 크기 및 주소의 의미는 컴파일러의 구현에 따라 다릅니다.  다른 형식에 대한 포인터가 동일한 길이가 되도록 보장되지 않습니다.  따라서 **sizeof\(char \*\)**가 **sizeof\(int \*\)**와 반드시 일치하는 것은 아닙니다.  
  
 **Microsoft 전용**  
  
 Microsoft C 컴파일러의 경우 **sizeof\(char \*\)**는 **sizeof\(int \*\)**와 일치합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [포인터 선언](../c-language/pointer-declarations.md)