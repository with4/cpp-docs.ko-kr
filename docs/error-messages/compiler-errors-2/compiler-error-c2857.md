---
title: "컴파일러 오류 C2857 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2857"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2857"
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2857
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ycfilename 명령줄 옵션과 함께 지정한 '\#include' 문이 소스 파일에 없습니다.  
  
 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) 옵션은 컴파일 중인 소스 파일에 포함되지 않은 포함 파일의 이름을 지정합니다.  
  
 이 오류는 조건부 컴파일 블록에서 컴파일되지 않은 `#include` 문으로 인해 발생할 수 있습니다.