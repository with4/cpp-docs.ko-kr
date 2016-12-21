---
title: "프로젝트에 미리 컴파일된 헤더 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "미리 컴파일된 헤더"
ms.assetid: 95010260-a035-4327-9d61-222016ac146c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트에 미리 컴파일된 헤더 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

앞의 단원에서는 미리 컴파일된 헤더의 개요, 즉 \/Yc와 \/Yu, \/Fp 옵션 및 [hdrstop](../../preprocessor/hdrstop.md) pragma에 대해 설명했습니다.  이 단원에서는 수동으로 미리 컴파일된 헤더 옵션을 프로젝트에 사용하기 위한 방법을 설명하고, 마지막 부분에서는 미리 컴파일된 헤더가 관리하는 코드 및 예제 메이크파일을 보여 줍니다.  
  
 수동으로 미리 컴파일된 헤더 옵션을 프로젝트에 사용하는 또 다른 방법을 보려면 Visual C\+\+의 기본 설치 시 만들어진 MFC\\SRC 디렉터리에 있는 메이크파일 중 하나를 참조하십시오.  이 메이크파일들은 이 단원에 설명된 것과 비슷한 방법을 사용하지만, Microsoft Program Maintenance Utility\(NMAKE\) 매크로를 보다 많이 사용하고 빌드 프로세스를 보다 잘 제어할 수 있도록 합니다.  
  
 이 섹션에서는 다음과 같은 항목을 설명합니다.  
  
-   [빌드 프로세스의 PCH 파일](../../build/reference/pch-files-in-the-build-process.md)  
  
-   [PCH용 샘플 메이크파일](../../build/reference/sample-makefile-for-pch.md)  
  
-   [PCH에 대한 예제 코드](../../build/reference/example-code-for-pch.md)  
  
## 참고 항목  
 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)