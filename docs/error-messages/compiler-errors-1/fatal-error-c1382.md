---
title: "심각한 오류 C1382 | Microsoft Docs"
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
  - "C1382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1382"
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'file' PCH 파일이 'obj'이\(가\) 생성된 후 다시 빌드되었습니다.이 개체를 다시 빌드하십시오.  
  
 [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)를 사용하여 컴파일했는데 컴파일러에서 .pch 파일을 가리키는 CIL .obj보다 최신 .pch 파일을 발견했습니다.  CIL .obj 파일의 정보가 최신 정보가 아닙니다.  개체를 다시 빌드하십시오.  
  
 **\/Yc**를 사용하여 컴파일하는 경우에도 C1382가 발생할 수 있지만 이 경우에도 컴파일러에 여러 개의 소스 코드 파일이 전달됩니다.  이 오류를 해결하려면 컴파일러에 여러 개의 소스 코드 파일을 전달할 때 **\/Yc**를 사용하지 마십시오.  자세한 내용은 [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md)을 참조하십시오.