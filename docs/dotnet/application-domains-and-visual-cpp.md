---
title: "응용 프로그램 도메인 및 Visual C++ | Microsoft Docs"
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
  - "/clr 컴파일러 옵션[C++], 응용 프로그램 도메인"
  - "응용 프로그램 도메인[C++], C++"
  - "interop[C++], 응용 프로그램 도메인"
  - "상호 운용성[C++], 응용 프로그램 도메인"
  - "혼합형 어셈블리[C++], 응용 프로그램 도메인"
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 응용 프로그램 도메인 및 Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`__clrcall` 가상 함수가 있으면 응용 프로그램 도메인\(appdomain\)별로 vtable이 생성됩니다.  appdomain 하나에서 개체를 만들면 해당 appdomain 내에서만 가상 함수를 호출할 수 있습니다.  **\/clr:pure** 컴파일 대상에 정의된 모든 함수는 `__clrcall` 호출 규칙을 사용합니다.  따라서 **\/clr:pure** 컴파일 대상에 정의된 모든 vtable은 appdomain별로 적용됩니다.  혼합 모드\(**\/clr**\)에서 형식에 `__clrcall` 가상 함수가 없으면 vtable이 프로세스별로 생성됩니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [\_\_clrcall](../cpp/clrcall.md)  
  
-   [방법: \/clr:pure로 마이그레이션](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [프로세스](../cpp/process.md)  
  
## 참고 항목  
 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)