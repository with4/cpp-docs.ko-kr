---
title: "컴파일러 오류 C2856 | Microsoft Docs"
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
  - "C2856"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2856"
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2856
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma hdrstop은 \#if 블록 내부에 있을 수 없습니다.  
  
 `hdrstop` pragma는 조건부 컴파일 블록의 본문 내부에 배치할 수 없습니다.  
  
 `#if/#endif` 블록에 포함되지 않은 영역으로 `#pragma hdrstop` 문을 옮기십시오.