---
title: "컴파일러 오류 C3715 | Microsoft Docs"
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
  - "C3715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3715"
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointer': 'class'에 대한 포인터이어야 합니다.  
  
 올바른 클래스를 가리키지 않는 포인터를 [\_\_hook](../../cpp/hook.md) 또는 [\_\_unhook](../../cpp/unhook.md)에 지정했습니다.  이 오류를 해결하려면 `__hook` 및 `__unhook` 호출이 올바른 클래스에 대한 포인터를 지정하도록 해야 합니다.