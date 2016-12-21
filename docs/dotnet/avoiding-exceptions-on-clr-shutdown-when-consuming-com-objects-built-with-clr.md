---
title: "/clr로 빌드한 COM 개체를 사용할 때 CLR 종료 시 예외 방지 | Microsoft Docs"
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
  - "/clr 컴파일러 옵션[C++], CLR 종료 예외"
  - "/clr 컴파일러 옵션[C++], COM 개체"
  - "CLR 종료 예외[C++]"
  - "interop[C++], CLR 종료 예외"
  - "상호 운용성[C++], CLR 종료 예외"
  - "혼합형 어셈블리[C++], CLR 종료 예외"
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# /clr로 빌드한 COM 개체를 사용할 때 CLR 종료 시 예외 방지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CLR\(공용 언어 런타임\)의 종료 모드가 시작되면 CLR 서비스에 대한 네이티브 함수의 액세스가 제한됩니다.  **\/clr**를 사용하여 컴파일한 COM 개체에 대해 Release를 호출하려고 하면 관리 코드에 정의되어 있는 IUnknown::Release 호출을 수행하기 위해 CLR가 네이티브 코드로 변환된 다음 관리 코드로 다시 변환됩니다.  종료 모드가 시작되면 CLR는 호출이 관리 코드에 다시 전달되지 않도록 막습니다.  
  
 이 문제를 해결하려면 Release 메서드에서 호출하는 소멸자에 네이티브 코드만 포함되어야 합니다.  
  
## 참고 항목  
 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)