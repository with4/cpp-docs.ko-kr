---
title: "XMMWORD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "XMMWORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XMMWORD directive"
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# XMMWORD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티미디어 피연산자의 128 비트 MMX 및 SSE \(XMM\) 지침과 함께 사용 합니다.  
  
## 구문  
  
```  
XMMWORD  
```  
  
## 설명  
 `XMMWORD`동일한 형식으로 나타내기 위한 것입니다 [\_\_m128](../../cpp/m128.md).  
  
## 예제  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```