---
title: "컴파일러 오류 C2773 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2773"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2773"
ms.assetid: 8d564b26-1623-4d92-aabc-dff33f7b1145
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2773
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import 및 \#using은 C\+\+ 컴파일러에서만 사용할 수 있습니다.  
  
 C 컴파일러는 `#import` 전처리기 지시문을 인식하지 않습니다.  소스를 C\+\+로 컴파일하십시오.  필요한 경우에는 [\/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)를 사용하십시오.