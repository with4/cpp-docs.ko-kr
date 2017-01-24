---
title: "컴파일러 경고 (수준 4) C4513 | Microsoft Docs"
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
  - "C4513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4513"
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 소멸자를 생성하지 못했습니다.  
  
 컴파일러에서 주어진 클래스에 대한 기본 소멸자를 생성할 수 없습니다.  소멸자가 파생 클래스에 액세스할 수 없는 기본 클래스에 있습니다.  기본 클래스에 전용 소멸자가 있으면 공용 또는 보호된 소멸자로 변경하십시오.