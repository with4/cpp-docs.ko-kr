---
title: "Visual Studio의 Visual C++ | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- visual c++
- visual c
- vc
dev_langs:
- C++
helpviewer_keywords:
- unmanaged code, C++
- development environment, Visual C++
- unmanaged code
- Visual C++
- Visual C++, reference
ms.assetid: e8dcc44c-a3e2-4ffe-887c-fd15b18dc458
caps.latest.revision: 61
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 220ecd24c6056737d0338cc584663e4664ac81b1
ms.openlocfilehash: 014391806f47e7d39ffe09e30feecaabe26f6a36

---
# <a name="visual-c-in-visual-studio"></a>Visual Studio의 Visual C++
Visual Studio 2017 프로그래밍 언어 및 개발 도구는 유니버설 Windows 앱, 네이티브 데스크톱 및 서버 응용 프로그램, Windows, Android, iOS에서 실행되는 플랫폼 간 라이브러리 및 .NET Framework에서 실행되는 관리되는 앱 개발에 도움이 될 수 있습니다.  
  
 **누구를 위한 설명서인가요?**  
  
 이 콘텐츠는 프로그램을 작성하는 C++ 개발자를 위한 내용입니다.  
  
-   프로그램을 실행할 수 있도록 C++ 재배포 가능 패키지 및 런타임 구성 요소를 찾고 있다면 [Microsoft 다운로드 센터](http://www.microsoft.com/en-us/download/) 로 이동하여 검색 상자에 **Visual C++** 를 입력합니다.  
  
-   C++ 프로그래밍 개념에 대한 소개를 찾고 있다면 이 콘텐츠를 제공하는 많은 웹 사이트 중 하나로 이동하거나 C++ 개발자인 Bjarne Stroustup이 제공하는 [프로그래밍 -- C++ 사용 원칙 및 사례(Second Edition)](http://stroustrup.com/Programming/) (영문) 복사본을 다운로드하세요. Visual C++ 콘텐츠에서는 사용자가 C++에 대한 기본적인 지식이 있는 것으로 가정합니다.  
  
-   Visual C++ 컴파일러를 찾고 있다면, [https://www.visualstudio.com/](https://www.visualstudio.com/)에서 Visual Studio 유료 또는 무료 버전을 다운로드해야 합니다.  

## <a name="general-information-about-visual-c"></a>Visual C++에 대한 일반 정보  
 [Visual C++의 새로운 기능](what-s-new-for-visual-cpp-in-visual-studio.md)  
 Visual C++의 새로운 기능을 알아봅니다.  

 [Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md) 
 Visual Studio 2017의 C++ 규칙 향상에 대해 알아봅니다. 

 [Visual C++ 변경 기록 2003 - 2015](porting/visual-cpp-change-history-2003-2015.md)  
 이전 버전의 주요 변경 내용에 대해 알아봅니다.  
  
 [C++의 진화](cpp/welcome-back-to-cpp-modern-cpp.md)  
 코드를 빠르고 안전하게 작성하고 C 스타일 프로그래밍에서 흔히 저지르는 많은 실수를 피할 수 있도록 C++11 및 C++14를 기반으로 C++ 프로그래밍 방법에 대해 자세히 알아봅니다.  
  
 [Visual C++ 도구 집합의 문제를 보고하는 방법](how-to-report-a-problem-with-the-visual-cpp-toolset.md)  
 Visual C++ 도구 집합(컴파일러, 링커 및 기타 도구)과 대조하여 효과적인 오류 보고서를 만드는 방법과 보고서를 전송하는 방법을 알아봅니다.  
  
 [Visual C++ 포팅 및 업그레이드 가이드](porting/visual-cpp-porting-and-upgrading-guide.md)  
 C++ 코드를 Windows 10 및 유니버설 Windows 플랫폼으로 포팅하는 작업을 포함하여 Visual Studio 2017에서 Visual C++로 코드를 포팅하고 프로젝트를 업그레이드하기 위한 지침입니다.  
  
 [C++11/14/17 기능에 대한 지원(최신 C++)](cpp/support-for-cpp11-14-17-features-modern-cpp.md)  
 Visual C++의 C++11 및 C++14 기능 지원에 대해 알아봅니다.  
  
 [Visual C++ 팀 블로그](http://blogs.msdn.com/b/vcblog/)  
 새로운 기능과 [!INCLUDE[vcprvc](build/includes/vcprvc_md.md)]의 개발자가 제공하는 최신 정보를 더 자세히 알아봅니다.  
  
 [Visual Studio 다운로드](http://go.microsoft.com/fwlink/?LinkId=235233)  
 Visual C++를 다운로드합니다.  
  
 [Visual Studio 버전의 Visual C++ 도구 및 기능](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)  
 여러 버전의 Visual Studio에 대해 알아봅니다.  
  
 [지원되는 플랫폼](supported-platforms-visual-cpp.md)  
 지원되는 플랫폼에 대해 알아봅니다.  
  
 [Visual C++ 샘플](visual-cpp-samples.md)  
 샘플에 대한 내용입니다.  
  
 [Visual Studio Community](http://go.microsoft.com/fwlink/?LinkId=235296)  
 Visual Studio에 대한 도움말을 보고 버그를 제출하고 제안을 하는 방법에 대해 알아봅니다.  
  
## <a name="writing-applications-in-c"></a>C++에서 응용 프로그램 작성  
 [유니버설 Windows 앱](windows/universal-windows-apps-cpp.md)  
 Windows 개발자 센터의 가이드 및 참조 내용을 알아봅니다. Windows 스토어 앱에 대한 자세한 내용은 [Visual Studio를 사용하여 Windows 스토어 앱 개발](http://go.microsoft.com/fwlink/p/?LinkId=248364) 및 [C++로 작성한 Windows 스토어 앱용 로드맵](http://go.microsoft.com/fwlink/p/?LinkId=244654)을 참조하세요.  
  
 [데스크톱 응용 프로그램(Visual C++)](windows/desktop-applications-visual-cpp.md)  
 메시지 루프 및 호출이 있는 데스크톱 응용 프로그램을 만드는 방법에 대해 알아봅니다.  
  
 [Visual C++의 DLL](build/dlls-in-visual-cpp.md)  
 Win32, ATL 및 MFC를 사용하여 Windows 데스크톱 DLL을 만드는 방법을 설명하고 DLL을 컴파일 및 등록하는 방법에 대해 알아봅니다.  
  
 [병렬 프로그래밍](parallel/parallel-programming-in-visual-cpp.md)  
 병렬 패턴 라이브러리, C++ AMP, OpenMP 및 Windows에서의 다중 스레딩과 관련된 기타 기능을 사용하는 방법에 대해 알아봅니다.  
  
 [보안 모범 사례](security/security-best-practices-for-cpp.md)  
 악의적 코드나 무단 사용으로부터 응용 프로그램을 보호하는 방법에 대해 알아봅니다.  
  
 [클라우드 및 웹 프로그래밍](cloud/cloud-and-web-programming-in-visual-cpp.md)  
 C++에는 웹 및 클라우드에 연결하기 위한 다양한 옵션이 있습니다.  
  
 [데이터 액세스](http://msdn.microsoft.com/Library/a9455752-39c4-4457-b14e-197772d3df0b)  
 ODBC 및 기타 데이터베이스 액세스 기술을 사용하여 데이터베이스에 연결합니다.  
  
 [텍스트 및 문자열](text/text-and-strings-in-visual-cpp.md)  
 현지 및 국제적 개발을 위한 다양한 텍스트 및 문자열 형식과 인코딩을 사용하는 방법을 알아봅니다.  
  
## <a name="c-development-tools"></a>C++ 개발 도구  
 프로젝트 만들기, 소스 코드 파일 사용, 라이브러리에 연결, 컴파일, 디버그, 프로파일링, 배포 등을 수행하는 방법을 알아보려면 [IDE 및 개발 도구](ide/ide-and-tools-for-visual-cpp-development.md)를 참조하세요.  
  
## <a name="c-language-reference"></a>C++ 언어 참조  
 C++ 언어에 대한 자세한 내용은 [C++ 언어 참조](cpp/cpp-language-reference.md)를 참조하세요.  
  
 C++ 전처리기에 대한 자세한 내용은 [C/C++ 전처리기 참조](preprocessor/c-cpp-preprocessor-reference.md)를 참조하세요.  
  
## <a name="c-libraries-in-visual-studio"></a>Visual Studio의 C++ 라이브러리  
 다음 섹션에서는 Visual C++와 함께 제공되는 다양한 C++ 라이브러리에 대한 정보를 제공합니다.  
  
 [C 런타임 라이브러리 참조](c-runtime-library/c-run-time-library-reference.md)  
 보안 문제가 있는 것으로 알려진 함수에 대해 보안을 강화한 대안을 포함합니다.  
  
 [C++ 표준 라이브러리](standard-library/cpp-standard-library-reference.md)  
 C++ 표준 라이브러리입니다.  
  
 [ATL(Active Template Library)](atl/atl-com-desktop-components.md)  
 COM 구성 요소 및 응용 프로그램을 지원합니다.  
  
 [MFC(Microsoft Foundation Class) 라이브러리](mfc/mfc-desktop-applications.md)  
 기존 또는 Office 스타일 사용자 인터페이스가 포함된 데스크톱 응용 프로그램 만들기를 지원합니다.  
  
 [PPL(병렬 패턴 라이브러리)](parallel/concrt/parallel-patterns-library-ppl.md)  
 CPU에서 실행되는 비동기 및 병렬 알고리즘입니다.  
  
 [C++ AMP(C++ Accelerated Massive Parallelism)](parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 GPU에서 실행되는 대규모 병렬 알고리즘입니다.  
  
 [WRL(Windows 런타임 템플릿 라이브러리)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
 [!INCLUDE[win8_appname_long](build/includes/win8_appname_long_md.md)] 응용 프로그램 및 구성 요소입니다.  
  
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
 CLR(공용 언어 런타임)에 대한 프로그래밍입니다.  
  
 [STL/CLR](dotnet/stl-clr-library-reference.md) 설명서 및 [C++ 지원 라이브러리](dotnet/cpp-support-library.md)를 참조하세요.  
  
## <a name="other-c-libraries"></a>기타 C++ 라이브러리  
 이 섹션에는 Visual Studio와 함께 제공되지 않고 다운로드하여 Visual C++와 함께 사용할 수 있는 라이브러리에 대한 링크가 있습니다.  
  
 [Boost](http://www.boost.org/)  
 인기 있고 널리 사용되는 라이브러리입니다.  
  
 [C++ REST SDK](http://casablanca.codeplex.com)  
 HTTP를 통해 웹 서비스와 통신하기 위한 Microsoft 라이브러리입니다.  
  
## <a name="more-resources"></a>추가 리소스  
 [Visual C++ 리소스](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Visual C++에 대한 추가 리소스  
  
 [표준 C++](http://isocpp.org/)  
 C++에 대해 알아보기, 최신 C++ 개요 살펴보기, 서적, 문서, 토론 및 이벤트 링크 찾기  
  
 [Visual C++ 살펴보기](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 C++를 배우기 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 언어 참조](c-language/c-language-reference.md)   
 [C 런타임 라이브러리 참조](c-runtime-library/c-run-time-library-reference.md)   
 [컴파일러 내장 및 어셈블리 언어](intrinsics/compiler-intrinsics-and-assembly-language.md)



<!--HONumber=Feb17_HO4-->


