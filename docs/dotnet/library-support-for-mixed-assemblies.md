---
title: "혼합형 어셈블리에 대한 라이브러리 지원 | Microsoft Docs"
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
  - "라이브러리[C++], 혼합형 어셈블리"
  - "혼합형 어셈블리[C++], 라이브러리 지원"
  - "msvcm90[d].dll"
  - "msvcmrt[d].lib"
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 혼합형 어셈블리에 대한 라이브러리 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서는 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일된 응용 프로그램에 대해 표준 C\+\+ 라이브러리, CRT\(C 런타임 라이브러리\), ATL 및 MFC를 사용할 수 있도록 지원합니다.  이렇게 하면 이러한 라이브러리를 사용하는 기존의 응용 프로그램에서 .NET Framework 기능도 사용할 수 있습니다.  
  
 이 버전에서는 다음과 같은 새로운 DLL 및 가져오기 라이브러리가 추가로 지원됩니다.  
  
-   \/clr을 사용하여 컴파일하는 경우 Msvcmrt\[d\].lib.  혼합형 어셈블리는 이 가져오기 라이브러리에 연결됩니다.  
  
-   \/clr:pure를 사용하여 컴파일하는 경우 Msvcm90\[d\].dll 및 Msvcurt\[d\].lib.  DLL은 관리되는 CRT\(C 런타임\) 지원을 제공하는 혼합형 어셈블리이며 GAC\(전역 어셈블리 캐시\)에 설치되는 관리되는 어셈블리의 일부입니다.  순수형 어셈블리는 이 가져오기 라이브러리에 연결되고 궁극적으로 Msvcm90.dll.에 바인딩됩니다.  
  
 이 지원 기능을 사용하면 이와 관련된 여러 가지 이점을 얻을 수 있습니다.  
  
-   CRT 및 표준 C\+\+ 라이브러리를 혼합 코드와 순수 코드에 모두 사용할 수 있습니다.  제공되는 CRT 및 표준 C\+\+ 라이브러리는 안정형이 아닙니다. 궁극적으로 사용자의 호출은 네이티브 코드에서 사용할 때와 동일한 CRT 및 표준 C\+\+ 라이브러리에 라우팅됩니다.  
  
-   순수 이미지와 혼합 이미지에서 올바른 통합 예외 처리를 수행할 수 있습니다.  
  
-   순수 이미지와 혼합 이미지에서 C\+\+ 변수를 정적으로 초기화할 수 있습니다.  
  
-   관리 코드에서 AppDomain별 변수와 프로세스별 변수를 지원합니다.  
  
-   Visual C\+\+ .NET 및 Visual C\+\+ .NET 2003에서 혼합 DLL에 발생하던 로더 잠금 문제를 해결할 수 있습니다.  
  
 그러나 이 지원 기능에는 다음과 같은 제한 사항이 있습니다.  
  
-   CRT DLL 모델만 지원됩니다. 이 제한 사항은 \/clr 또는 \/clr:pure로 컴파일된 코드에 모두 적용됩니다.  
  
-   해당 개체에서 Visual C\+\+ 라이브러리를 사용하는 경우 단일 이미지에 순수 개체와 혼합 개체를 함께 사용할 수 없습니다. 순수 이미지에서 모든 개체는 순수 개체여야 하기 때문입니다.  이와 같이 개체를 혼합하면 링크 타임 오류가 발생합니다.  
  
 이전 버전의 CLR\(공용 언어 런타임\)을 사용하면 올바르게 작동하지 않을 수 있으므로 CLR을 최신 버전으로 업데이트해야 합니다.  이러한 변경 내용을 적용하여 빌드된 코드는 CLR 버전 1.x에서 실행되지 않습니다.  
  
## 참고 항목  
 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)