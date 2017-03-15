---
title: "링커 도구 오류 LNK2017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2017"
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 오류 LNK2017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/LARGEADDRESSAWARE:NO가 없으므로 'symbol' 재배치\(대상: 'segment'\)가 잘못되었습니다.  
  
 32비트 주소를 사용하여 64비트 이미지를 빌드하려고 합니다.  다음을 수행하면 빌드할 수 있습니다.  
  
-   고정 로드 주소를 사용합니다.  
  
-   이미지를 3GB로 제한합니다.  
  
-   [\/largeaddressaware:no](../../build/reference/largeaddressaware-handle-large-addresses.md)를 지정합니다.