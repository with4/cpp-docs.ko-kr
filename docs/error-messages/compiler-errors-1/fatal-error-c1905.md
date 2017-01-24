---
title: "심각한 오류 C1905 | Microsoft Docs"
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
  - "C1905"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1905"
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1905
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프런트 엔드와 백 엔드가 호환되지 않습니다. 같은 프로세서를 대상으로 해야 합니다.  
  
 이 오류는 x86, ARM 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]와 같은 하나의 프로세서를 대상으로 하는 컴파일러 프런트 엔드\(C1.dll\)에서 .obj 파일이 생성되지만 다른 프로세서를 대상으로 하는 백 엔드\(C2.dll\)에서 이 파일을 읽는 중일 경우에 발생합니다.  
  
 이 문제를 해결하려면 사용 중인 프런트 엔드와 백 엔드가 일치하는지 확인합니다.  Visual Studio에서 만든 프로젝트의 경우 기본적으로 일치하는 프런트 엔드와 백 엔드가 사용됩니다.  컴파일러 도구에 대해 다른 경로를 사용하도록 프로젝트 파일을 편집한 경우 이 오류가 발생할 수 있습니다.  컴파일러 도구의 경로를 구체적으로 설정하지 않은 경우 설치한 Visual Studio가 손상되면 이 오류가 발생할 수 있습니다.  컴파일러 .dll 파일을 한 위치에서 다른 위치로 복사한 경우를 예로 들 수 있습니다.  Windows 제어판의 **프로그램 및 기능**을 사용하여 Visual Studio를 복구하거나 다시 설치합니다.