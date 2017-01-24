---
title: "컴파일러 오류 C3728 | Microsoft Docs"
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
  - "C3728"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3728"
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3728
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': 이벤트에 raise 메서드가 없습니다.  
  
 이벤트가 정의된 클래스 외부에서 발생하지 못하도록 하는 언어\(예: C\#\)를 사용하여 만든 메타데이터가 [\#using](../../preprocessor/hash-using-directive-cpp.md) 지시문을 통해 포함되었으며, CLR 프로그래밍을 사용하는 Visual C\+\+ 프로그램이 이벤트를 발생시키려고 했습니다.  
  
 C\#과 같은 언어로 개발한 프로그램에서 이벤트를 발생시키려면 이벤트를 포함하는 클래스가 이벤트를 발생시키는 공용 메서드를 정의해야 합니다.