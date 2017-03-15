---
title: "혼합형, 순수형 및 안정형 기능 비교(C++/CLI) | Microsoft Docs"
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
  - "혼합형 어셈블리[C++]"
  - "혼합형 어셈블리[C++], 순수형 어셈블리와 비교"
  - "혼합형 어셈블리[C++], 안전형 MSIL과 비교"
  - "순수형 어셈블리[C++]"
  - "순수형 MSIL[C++]"
  - "순수형 MSIL[C++], 혼합형 및 안전형 MSIL과 비교"
  - "순수형 MSIL[C++], 혼합형 어셈블리와 비교"
  - "순수형 MSIL[C++], 안전형 MSIL과 비교"
  - "안전형 어셈블리[C++]"
  - "안전형 어셈블리[C++], 혼합형 어셈블리와 비교"
  - "안전형 어셈블리[C++], 순수형 어셈블리와 비교"
  - "안정형 어셈블리[C++]"
  - "안정형 어셈블리[C++], 혼합형 어셈블리와 비교"
  - "안정형 어셈블리[C++], 순수형 어셈블리와 비교"
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 혼합형, 순수형 및 안정형 기능 비교(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 서로 다른 **\/clr** 컴파일 모드 사이의 기능을 비교합니다.  자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
## 기능 비교  
  
|기능|혼합형\(\/clr\)|순수형\(\/clr:pure\)|안전\(\/clr:safe\)|관련 정보|  
|--------|------------------|-----------------------|----------------------|-----------|  
|CRT 라이브러리|지원됨|지원됨||[범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)|  
|MFC\/ATL|지원됨|||[MFC 데스크톱 응용 프로그램](../mfc/mfc-desktop-applications.md) &#124; [Class Overview](../atl/atl-class-overview.md)|  
|관리되지 않는 함수|지원됨|||[혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)|  
|관리되지 않는 데이터|지원됨|지원됨||[순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)|  
|관리되지 않는 함수에서 호출|지원됨|||[방법: \/clr:pure로 마이그레이션](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)|  
|관리되지 않는 함수 호출 지원|지원됨|C 스타일 함수만|P\/Invoke만|[C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|  
|리플렉션 지원|DLL만|지원됨|지원됨|[리플렉션](../dotnet/reflection-cpp-cli.md)|  
  
## 참고 항목  
 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)