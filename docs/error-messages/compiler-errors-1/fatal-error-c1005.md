---
title: "심각한 오류 C1005 | Microsoft Docs"
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
  - "C1005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1005"
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

버퍼에 비해 문자열이 너무 깁니다.  
  
 컴파일러 중간 파일의 문자열에서 버퍼를 오버플로했습니다.  
  
 [\/Fd](../../build/reference/fd-program-database-file-name.md) 또는 [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 컴파일러 옵션으로 전달한 매개 변수가 256바이트보다 큰 경우 이 오류가 표시될 수 있습니다.