---
title: Visual Studio의 Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- unmanaged code, C++
- development environment, Visual C++
- unmanaged code
- Visual C++
- Visual C++, reference
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d4f09ebe0cfaca9bb742baa902a256ac0f92996
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="visual-c-in-visual-studio"></a>Visual Studio의 Visual C++

일반적으로 Visual C++ 또는 MSVC라고 줄여부르는 Microsoft Visual C++는 C++, C 및 어셈블리 언어 개발 도구 및 Windows에서 Visual Studio의 일부로 사용할 수 있는 라이브러리의 이름입니다. 이러한 도구 및 라이브러리를 통해 UWP(유니버설 Windows 플랫폼) 앱, 네이티브 Windows 데스크톱 및 서버 응용 프로그램, Windows, Linux, Android 및 iOS에서 실행되는 플랫폼 간 라이브러리 및 앱뿐만 아니라 .NET Framework를 사용하는 관리 앱 및 라이브러리를 만들 수 있습니다. Visual C++를 사용하여 간단한 콘솔 앱 항목부터 Windows 데스크톱용 가장 정교하고 복잡한 앱, 장치 드라이버 및 운영 체제 구성 요소부터 모바일 장치용 플랫폼 간 게임, 가장 작은 IoT 장치부터 Azure 클라우드의 다중 서버 성능 컴퓨팅 기능을 작성할 수 있습니다.

## <a name="general-information-about-visual-c"></a>Visual C++에 대한 일반 정보

[Visual C++의 새로운 기능](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
Visual C++의 새로운 기능을 알아봅니다.

[Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md)<br/>
Visual Studio 2017의 C++ 규칙 향상에 대해 알아봅니다.

[Visual C++ 언어 규칙](visual-cpp-language-conformance.md)<br/>
MSVC C++ 컴파일러의 기능별 규칙 상태 목록입니다.

[Visual C++ 변경 기록 2003 - 2015](porting/visual-cpp-change-history-2003-2015.md)<br/>
이전 버전의 주요 변경 내용에 대해 알아봅니다.

[C++의 진화](cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
코드를 빠르고 안전하게 작성하고 C 스타일 프로그래밍에서 흔히 저지르는 많은 실수를 피할 수 있도록 C++11 및 C++14를 기반으로 C++ 프로그래밍 방법에 대해 자세히 알아봅니다.

[Visual C++ 도구 집합의 문제를 보고하는 방법](how-to-report-a-problem-with-the-visual-cpp-toolset.md)<br/>
Visual C++ 도구 집합(컴파일러, 링커 및 기타 도구)과 대조하여 효과적인 오류 보고서를 만드는 방법과 보고서를 전송하는 방법을 알아봅니다.

[Visual C++ 포팅 및 업그레이드 가이드](porting/visual-cpp-porting-and-upgrading-guide.md)<br/>
C++ 코드를 Windows 10 및 유니버설 Windows 플랫폼으로 포팅하는 작업을 포함하여 코드를 포팅하고 프로젝트를 Visual Studio 2017로 업그레이드하기 위한 지침입니다.

[Visual C++ 팀 블로그](http://blogs.msdn.com/b/vcblog/)<br/>
새로운 기능과 [!INCLUDE[vcprvc](build/includes/vcprvc_md.md)]의 개발자가 제공하는 최신 정보를 더 자세히 알아봅니다.

[Visual Studio 다운로드](http://go.microsoft.com/fwlink/p/?linkid=235233)<br/>
Visual Studio 다운로드

[Visual Studio 버전의 Visual C++ 도구 및 기능](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)<br/>
여러 버전의 Visual Studio에 대해 알아봅니다.

[지원되는 플랫폼](supported-platforms-visual-cpp.md)<br/>
지원되는 플랫폼에 대해 알아봅니다.

[Visual C++ 샘플](visual-cpp-samples.md)<br/>
샘플에 대한 내용입니다.

[Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)<br/>
Visual Studio에 대한 도움말을 보고 버그를 제출하고 제안을 하는 방법에 대해 알아봅니다.

## <a name="writing-applications-in-c"></a>C++에서 응용 프로그램 작성

[유니버설 Windows 앱](windows/universal-windows-apps-cpp.md)<br/>
Windows 개발자 센터의 가이드 및 참조 내용을 알아봅니다. UWP 앱 개발에 대한 자세한 내용은 [유니버설 Windows 플랫폼 소개](/windows/uwp/get-started/universal-application-platform-guide) 및 [C++을 사용하여 첫 번째 UWP 앱 만들기](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)를 참조하세요.

[데스크톱 응용 프로그램(C++)](windows/desktop-applications-visual-cpp.md)<br/>
메시지 루프 및 호출이 있는 데스크톱 응용 프로그램을 만드는 방법에 대해 알아봅니다.

[Visual C++의 DLL](build/dlls-in-visual-cpp.md)<br/>
Win32, ATL 및 MFC를 사용하여 Windows 데스크톱 DLL을 만드는 방법을 설명하고 DLL을 컴파일 및 등록하는 방법에 대해 알아봅니다.

[병렬 프로그래밍](parallel/parallel-programming-in-visual-cpp.md)<br/>
병렬 패턴 라이브러리, C++ AMP, OpenMP 및 Windows에서의 다중 스레딩과 관련된 기타 기능을 사용하는 방법에 대해 알아봅니다.

[보안 모범 사례](security/security-best-practices-for-cpp.md)<br/>
악의적 코드나 무단 사용으로부터 응용 프로그램을 보호하는 방법에 대해 알아봅니다.

[클라우드 및 웹 프로그래밍](cloud/cloud-and-web-programming-in-visual-cpp.md)<br/>
C++에는 웹 및 클라우드에 연결하기 위한 다양한 옵션이 있습니다.

[데이터 액세스](data/data-access-in-cpp.md)<br/>
ODBC 및 기타 데이터베이스 액세스 기술을 사용하여 데이터베이스에 연결합니다.

[텍스트 및 문자열](text/text-and-strings-in-visual-cpp.md)<br/>
현지 및 국제적 개발을 위한 다양한 텍스트 및 문자열 형식과 인코딩을 사용하는 방법을 알아봅니다.

## <a name="c-development-tools"></a>C++ 개발 도구

프로젝트 만들기, 소스 코드 파일 사용, 라이브러리에 연결, 컴파일, 디버그, 프로파일링, 배포 등을 수행하는 방법을 알아보려면 [IDE 및 개발 도구](ide/ide-and-tools-for-visual-cpp-development.md)를 참조하세요.

## <a name="c-language-reference"></a>C++ 언어 참조

C++ 언어에 대한 자세한 내용은 [C++ Language Reference](cpp/cpp-language-reference.md)를 참조하세요.

C++ 전처리기에 대한 자세한 내용은 [C/C++ Preprocessor Reference](preprocessor/c-cpp-preprocessor-reference.md)를 참조하세요.

## <a name="c-libraries-in-visual-studio"></a>Visual Studio의 C++ 라이브러리

다음 섹션에서는 Visual Studio에서 제공되는 다양한 C 및 C++ 라이브러리에 대한 정보를 제공합니다.

[C 런타임 라이브러리 참조](c-runtime-library/c-run-time-library-reference.md)<br/>
보안 문제가 있는 것으로 알려진 함수에 대해 보안을 강화한 대안을 포함합니다.

[C++ 표준 라이브러리](standard-library/cpp-standard-library-reference.md)<br/>
C++ 표준 라이브러리입니다.

[ATL(액티브 템플릿 라이브러리)](atl/atl-com-desktop-components.md)<br/>
COM 구성 요소 및 응용 프로그램을 지원합니다.

[MFC(Microsoft Foundation Class) 라이브러리](mfc/mfc-desktop-applications.md)<br/>
기존 또는 Office 스타일 사용자 인터페이스가 포함된 데스크톱 응용 프로그램 만들기를 지원합니다.

[PPL(병렬 패턴 라이브러리)](parallel/concrt/parallel-patterns-library-ppl.md)<br/>
CPU에서 실행되는 비동기 및 병렬 알고리즘입니다.

[C++ AMP(C++ Accelerated Massive Parallelism)](parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
GPU에서 실행되는 대규모 병렬 알고리즘입니다.

[WRL(Windows 런타임 템플릿 라이브러리)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)<br/>
UWP(유니버설 Windows 플랫폼) 앱 및 구성 요소

[C++/CLI를 사용한 .NET 프로그래밍](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
CLR(공용 언어 런타임)에 대한 프로그래밍입니다.

[STL/CLR](dotnet/stl-clr-library-reference.md) 설명서 및 [C++ Support Library](dotnet/cpp-support-library.md)를 참조하세요.

## <a name="other-c-libraries"></a>기타 C++ 라이브러리

vcpkg 명령줄 도구를 사용하여 600개가 넘는 C++ 오픈 소스 라이브러리를 검색 및 설치하는 작업을 상당히 간소화할 수 있습니다. [vcpkg: Windows용 C++ 패키지 관리자](vcpkg.md)를 참조하세요.

## <a name="more-resources"></a>추가 리소스

[표준 C++](http://isocpp.org/)<br/>
C++에 대해 알아보기, 최신 C++ 개요 살펴보기, 서적, 문서, 토론 및 이벤트 링크 찾기

[Visual C++ 살펴보기](http://msdn.microsoft.com/vstudio/hh386302.aspx)<br/>
C++를 배우기 시작합니다.

## <a name="see-also"></a>참고 항목

- [C# 언어 참조](c-language/c-language-reference.md)
- [C 런타임 라이브러리 참조](c-runtime-library/c-run-time-library-reference.md)
- [컴파일러 내장 및 어셈블리 언어](intrinsics/compiler-intrinsics-and-assembly-language.md)
