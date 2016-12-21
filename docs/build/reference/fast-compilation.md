---
title: "컴파일 속도 향상 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 성능"
  - "컴파일, 성능"
  - "빠른 컴파일"
  - "성능, cle.exe 컴파일러"
ms.assetid: 5fead136-ba69-40c8-8e25-236f89d5990a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일 속도 향상
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일 속도를 높이려면  
  
-   [최소 재빌드](../../build/reference/gm-enable-minimal-rebuild.md)를 사용합니다. 이 방법을 사용하면 C\+\+ 컴파일러에서는 헤더 파일에 있는 클래스에 대한 변경 사항과 관계 없는 경우에만 소스 파일을 다시 컴파일합니다.  
  
-   [미리 컴파일된 헤더 파일을 만들고](../../build/reference/creating-precompiled-header-files.md) [미리 컴파일된 헤더 옵션](../../build/reference/yc-create-precompiled-header-file.md)을 사용합니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)