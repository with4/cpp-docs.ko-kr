---
title: "Windows 런타임 지원되지 않는 CRT 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "지원되지 않는 CRT 함수, Windows 런타임"
  - "Windows 런타임, 지원되지 않는 CRT 함수"
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Windows 런타임 지원되지 않는 CRT 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대부분 CRT\(C 런타임\) API는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서 실행되는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱에서 사용할 수 없습니다.  이들 앱은 \/ZW 컴파일러 플래그를 사용하여 빌드합니다.  지원되지 않는 CRT 함수 목록을 보려면 [\/ZW에서 지원되지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
 모든 CRT API는 설명서의 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md) 섹션에서 설명됩니다.  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)