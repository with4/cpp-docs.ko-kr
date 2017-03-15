---
title: "MMWORD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MMWORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MMWORD directive"
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# MMWORD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티미디어 피연산자의 64 비트 MMX 및 SSE \(XMM\) 지침과 함께 사용 합니다.  
  
## 구문  
  
```  
MMWORD  
```  
  
## 설명  
 `MMWORD`형식이입니다.  MASM에 추가 되 고 MMWORD 하기 전에 동일한 기능으로 달성 수 있습니다.:  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 피연산자가 64 비트에 두 지침을 작업 하는 동안 `QWORD` 는 64 비트 부호 없는 정수 형식입니다 및 `MMWORD` 멀티미디어 64 비트 값입니다.  
  
 `MMWORD`동일한 형식으로 나타내기 위한 것입니다 [\_\_m64](../../cpp/m64.md).  
  
## 예제  
  
```  
movq     mm0, mmword ptr [ebx]  
```