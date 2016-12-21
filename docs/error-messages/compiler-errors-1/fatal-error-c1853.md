---
title: "심각한 오류 C1853 | Microsoft Docs"
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
  - "C1853"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1853"
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1853
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 미리 컴파일된 헤더 파일이 이전 버전의 컴파일러에서 만들어졌거나, 미리 컴파일된 헤더가 C\+\+인데 C에서 사용하고 있거나 또는 그 반대의 경우입니다.  
  
 가능한 원인  
  
-   미리 컴파일된 헤더가 이전 컴파일러 버전으로 컴파일되었습니다.  헤더를 현재 컴파일러로 다시 컴파일해 보십시오.  
  
-   미리 컴파일된 헤더가 C\+\+인데 이를 C에서 사용하고 있습니다.  [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션 중 하나를 지정하거나 소스 파일의 접미사를 "c"로 변경하여 헤더를 C에서 사용할 수 있도록 다시 컴파일해 보십시오.  자세한 내용은 [코드를 미리 컴파일하기 위한 두 가지 선택 사항](../../build/reference/two-choices-for-precompiling-code.md)을 참조하십시오.