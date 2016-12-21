---
title: "링커 도구 오류 LNK2008 | Microsoft Docs"
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
  - "LNK2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2008"
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

픽스업 대상이 'symbol\_name'에 맞춰지지 않습니다.  
  
 LINK가 개체 파일에서 제대로 맞춰지지 않은 픽스업 대상을 발견했습니다.  
  
 이 오류는 사용자 지정 섹션 맞춤\(예: \#pragma [pack](../../preprocessor/pack.md)\), [align](../../cpp/align-cpp.md) 한정자 또는 섹션 맞춤을 수정하는 어셈블리 언어 코드를 사용하는 경우에 발생할 수 있습니다.  
  
 코드에 이러한 항목을 사용하지 않았다면 오류의 원인이 컴파일러에 있을 수 있습니다.