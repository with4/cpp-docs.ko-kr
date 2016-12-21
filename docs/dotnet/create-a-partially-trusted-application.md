---
title: "방법: CRT 라이브러리 DLL에 대한 종속성을 제거하여 부분적으로 신뢰할 수 있는 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr 컴파일러 옵션[C++], 부분 신뢰 응용 프로그램"
  - "interop[C++], 부분 신뢰 응용 프로그램"
  - "상호 운용성[C++], 부분 신뢰 응용 프로그램"
  - "혼합형 어셈블리[C++], 부분 신뢰 응용 프로그램"
  - "msvcm90[d].dll"
  - "부분 신뢰 응용 프로그램[C++]"
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: CRT 라이브러리 DLL에 대한 종속성을 제거하여 부분적으로 신뢰할 수 있는 응용 프로그램 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 msvcm90.dll에 대한 종속성을 제거하고 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]를 사용하여 부분적으로 신뢰할 수 있는 공용 언어 런타임 응용 프로그램을 만드는 방법에 대해 설명합니다.  
  
 **\/clr**을 사용하여 빌드한 Visual C\+\+ 응용 프로그램은 C 런타임 라이브러리의 일부인 msvcm90.dll에 종속됩니다.  부분 신뢰 환경에서 응용 프로그램을 사용하려는 경우 CLR은 DLL에 특정 코드 액세스 보안 규칙을 적용합니다.  msvcm90.dll에 네이티브 코드가 포함되어 있고 코드 액세스 보안 정책을 여기에 적용할 수 없으므로 이 종속성을 제거해야 합니다.  
  
 응용 프로그램에서 어떠한 C 런타임 라이브러리 기능도 사용하지 않으며 코드에서 이 라이브러리에 대한 종속성을 제거하려는 경우에는 **\/NODEFAULTLIB:msvcmrt.lib** 링커 옵션을 사용하여 ptrustm.lib 또는 ptrustmd.lib를 연결해야 합니다.  이러한 라이브러리에는 응용 프로그램의 초기화 및 초기화 해제에 필요한 개체 파일, 초기화 코드에 사용되는 예외 클래스 및 관리되는 예외 처리 코드가 들어 있습니다.  이러한 라이브러리 중 하나에 연결하면 msvcm90.dll.에 대한 종속성이 모두 제거됩니다.  
  
> [!NOTE]
>  어셈블리의 초기화 해제 순서는 ptrust 라이브러리를 사용하는 응용 프로그램에 따라 다를 수 있습니다.  일반적인 응용 프로그램의 경우 어셈블리는 대개 로드된 순서와 반대로 해제되지만 반드시 그런 것은 아닙니다.  부분 신뢰 응용 프로그램의 경우 어셈블리는 대개 로드될 때와 동일한 순서로 해제됩니다.  그러나 이 순서 또한 반드시 지켜지는 것은 아닙니다.  
  
### 부분적으로 신뢰할 수 있는 혼합\(\/clr\) 응용 프로그램을 만들려면  
  
1.  msvcm90.dll,에 대한 종속성을 제거하려면 **\/NODEFAULTLIB:msvcmrt.lib** 링커 옵션을 사용하여 이 라이브러리를 포함하지 않도록 링커에 알려야 합니다.  Visual Studio 개발 환경을 사용하거나 프로그래밍 방식으로 이를 수행하는 방법에 대한 자세한 내용은 [\/NODEFAULTLIB\(라이브러리 무시\)](../build/reference/nodefaultlib-ignore-libraries.md)를 참조하십시오.  
  
2.  ptrustm 라이브러리 중 하나를 링커 입력 종속성에 추가합니다.  응용 프로그램을 릴리스 모드에서 빌드하는 경우 ptrustm.lib를 사용합니다.  디버그 모드의 경우 ptrustmd.lib를 사용합니다.  Visual Studio 개발 환경을 사용하거나 프로그래밍 방식으로 이를 수행하는 방법에 대한 자세한 내용은 [링커 입력 파일로 사용하는 .Lib 파일](../build/reference/dot-lib-files-as-linker-input.md)를 참조하십시오.  
  
## 참고 항목  
 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)   
 [혼합형 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md)   
 [혼합형 어셈블리에 대한 라이브러리 지원](../dotnet/library-support-for-mixed-assemblies.md)   
 [\/link\(옵션을 링커로 전달\)](../build/reference/link-pass-options-to-linker.md)   
 [PAVE Security in Native and .NET Framework Code](http://msdn.microsoft.com/ko-kr/bd61be84-c143-409a-a75a-44253724f784)