---
title: "링커 도구 오류 LNK2026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2026"
ms.assetid: 9955bf7c-59b5-4fa1-8481-147db0d7df45
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 링커 도구 오류 LNK2026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모듈이 SAFESEH 이미지에 대해 안전하지 않습니다.  
  
 [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)가 지정되었지만 모듈이 안전한 예외 처리 기능과 호환되지 않습니다.  이 모듈에 **\/SAFESEH** 옵션을 사용하려면 Visual C\+\+ .NET 2003 이상 버전의 컴파일러를 사용하여 모듈을 다시 컴파일해야 합니다.