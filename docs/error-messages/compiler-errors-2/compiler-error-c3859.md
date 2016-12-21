---
title: "컴파일러 오류 C3859 | Microsoft Docs"
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
  - "C3859"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3859"
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3859
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PCH에 대한 가상 메모리 범위를 초과했습니다. 명령줄 옵션을 '\-Zmvalue' 이상으로 지정하여 다시 컴파일하세요.  
  
 미리 컴파일된 헤더가 컴파일러에서 넣으려는 데이터의 양에 비해 너무 작습니다.  **\/Zm** 컴파일러 플래그를 사용하여 미리 컴파일된 헤더 파일에 대해 더 큰 값을 지정하세요.  자세한 내용은 [\/Zm\(메모리 할당 제한 지정\)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)을 참조하세요.