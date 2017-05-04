---
title: "Visual C++ 언어 참조(C++-CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
caps.latest.revision: 27
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 27
---
# Visual C++ 언어 참조(C++-CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]\([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\)은 최신 C\+\+와 가능한 가까운 형식의 Windows 앱 및 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소를 만드는 데 사용되는 C\+\+ 언어의 확장 집합입니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]를 사용하여 Visual C\#, Visual Basic, JavaScript 및 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]을 지원하는 다른 언어와 쉽게 상호 작용하는 네이티브 코드로 Windows 앱 및 구성 요소를 작성할 수 있습니다. 드물지만 원시 COM 인터페이스 또는 예외가 없는 코드에 직접 액세스해야 하는 경우 [Windows 런타임 C\+\+ 템플릿 라이브러리\(WRL\)](~/windows/windows-runtime-cpp-template-library-wrl.md)를 사용할 수 있습니다.  
  
 새 모델은 차세대 Windows 네이티브 C\+\+ 프로그래밍을 나타냅니다. 이를 통해 다음을 만들 수 있습니다.  
  
-   사용자 인터페이스를 정의하고 네이티브 스택을 사용하는 XAML을 사용하는 C\+\+ Windows 앱. 자세한 내용은 [C\+\+에서 "hello world" 앱 만들기\(Windows 10\)](http://msdn.microsoft.com/library/windows/apps/dn996906.aspx)를 참조하세요.  
  
-   JavaScript 기반 Windows 앱에서 사용할 수 있는 C\+\+ [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소. 자세한 내용은 [C\+\+에서 Windows 런타임 구성 요소 만들기](http://msdn.microsoft.com/library/hh441569.aspx)[C\+\+로 Windows Runtime 구성 요소 만들기](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)를 참조하세요.  
  
-   Windows DirectX 게임 및 그래픽 위주 앱. 자세한 내용은 [DirectX로 간단한 범용 Windows 플랫폼\(UWP\) 게임 만들기](http://msdn.microsoft.com/library/windows/apps/xaml/mt210793.aspx)를 참조하세요.  
  
## 관련 문서  
  
|||  
|-|-|  
|[빠른 참조](../cppcx/quick-reference-c-cx.md)|[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]\([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\)의 키워드 및 연산자 표|  
|[형식 시스템](../cppcx/type-system-c-cx.md)|기본 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 형식 및 프로그래밍 구조체와 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]를 활용하여 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식을 사용하고 만드는 방법을 설명합니다.|  
|[응용 프로그램 및 라이브러리 빌드](../cppcx/building-apps-and-libraries-c-cx.md)|IDE를 사용하여 정적 라이브러리 및 DLL에 대한 링크와 응용 프로그램을 빌드하는 방법을 설명합니다.|  
|[다른 언어와의 상호 운용](../cppcx/interoperating-with-other-languages-c-cx.md)|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]를 사용하여 작성된 구성 요소를 JavaScript, 관리되는 언어 또는 [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)]로 작성된 구성 요소와 함께 사용하는 방법을 설명합니다.|  
|[스레딩 및 마샬링](../cppcx/threading-and-marshaling-c-cx.md)|사용자가 만든 구성 요소의 스레딩 및 마샬링 동작을 지정하는 방법을 설명합니다.|  
|[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)|기본 네임스페이스, Platform 네임스페이스, Platform::Collections 및 관련 네임스페이스에 대한 참조 설명서입니다.|  
|[유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows 런타임 앱에서 사용할 수 없는 CRT 함수를 나열합니다.|  
|[Windows 10 앱에 대한 방법 가이드](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Windows 10 앱에 대한 개략적인 지침 및 자세한 정보에 대한 링크를 제공합니다.|  
  
1.  [C \+ \+ \/CX 파트 0 \/ \[n\]: 소개](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
2.  [C \+ \+ \/CX 파트 0 \/ \[n\]: 소개](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
3.  [C \+ \+ \/CX 파트 2 \/ \[n\]: 모자를 쓰는 유형](http://blogs.msdn.com/b/vcblog/archive/2012/09/17/cxxcxpart02typesthatwearhats.aspx)  
  
4.  [C \+ \+ \/CX 파트 3 \/ \[n\]: 작성 중](http://blogs.msdn.com/b/vcblog/archive/2012/10/05/cxxcxpart03underconstruction.aspx)  
  
5.  [C \+ \+ \/CX 파트 4 \/ \[n\]: 정적 멤버 함수](http://blogs.msdn.com/b/vcblog/archive/2012/10/19/cxxcxpart04staticmemberfunctions.aspx)