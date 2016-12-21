---
title: "BSCMAKE 오류 BK1509 | Microsoft Docs"
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
  - "BK1509"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1509"
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE 오류 BK1509
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙 공간이 부족합니다.  
  
 BSCMAKE에 가상 메모리를 포함하여 메모리가 부족합니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  일부 디스크 공간을 비웁니다.  
  
2.  스왑 파일 크기를 증가시킵니다.  
  
3.  Windows 스왑 파일의 크기를 늘입니다.  
  
4.  \/Ei 또는 \/Es로 BSCMAKE가 필요한 메모리를 줄여 일부 입력 파일을 제거하거나 \/Em으로 매크로 본문을 제거합니다.