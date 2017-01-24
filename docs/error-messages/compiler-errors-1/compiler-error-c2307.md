---
title: "컴파일러 오류 C2307 | Microsoft Docs"
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
  - "C2307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2307"
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

증분 컴파일이 활성화된 경우 'pragma' pragma를 함수 외부로 이동해야 합니다.  
  
 증분 컴파일을 사용 중이면 `data_seg` pragma를 함수 사이에 배치해야 합니다.