---
title: "링커 도구 오류 LNK1166 | Microsoft Docs"
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
  - "LNK1166"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1166"
ms.assetid: d69548a8-0efb-44e1-90b7-b27636a4b575
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1166
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

offset\=offset, va\=value에서 코드를 조정할 수 없습니다.  
  
 LINK가 코드를 필요한 대로 패딩하지 못했습니다.  
  
 일부 프로세서에서는 페이지 경계를 교차하는 데 특정 명령을 사용할 수 없습니다.  LINK는 패드를 추가하여 이 오류를 수정하려고 합니다.  이 경우에는 LINK가 문제를 해결하지 못했습니다.