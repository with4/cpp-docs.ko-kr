---
title: Visual c + + 언어 참조 (C + + /cli CX) | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b251a89eee456905fae1e2096a74362fc6c44ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="visual-c-language-reference-ccx"></a>Visual C++ 언어 참조(C++/CX)

C + + /cli CX는 집합의 Windows 앱 및 Windows 런타임 구성 요소를 최신 가능한 c + + 가까운를 만들 수 있도록 하는 c + + 언어 확장입니다. 사용 하 여 C + + /CX를 Visual C#, Visual Basic 및 JavaScript와 쉽게 상호 작용 하는 네이티브 코드와 Windows 런타임을 지 원하는 다른 언어에서 Windows 앱 및 구성 요소를 작성 합니다. 드물지만 원시 COM 인터페이스 또는 예외가 없는 코드에 직접 액세스 해야 하는 경우를 사용할 수 있습니다는 [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)합니다.

> [!NOTE]
> C + + /cli WinRT는 새, 표준 C + + 17 언어 프로젝션 Windows 런타임 Api에 대 한 합니다. 최신 Windows 10 SDK 부터는 1803 버전에서 제공 됩니다. C + + /cli WinRT 헤더 파일에서 완전히 구현 되며 하 게 고급 액세스 권한이 있는 최신 Windows API를 제공 합니다.

> C + + /cli WinRT, 둘 다 사용 하는 모든 표준 호환 C + + 17 컴파일러를 사용 하 여 Windows 런타임 Api를 작성 합니다. C + + /cli WinRT에서 일반적으로 더 나은 성능을 제공 하 고 Windows 런타임에 대 한 다른 언어 옵션 보다 더 작은 이진 파일을 생성 합니다. 우리는 계속 지원 C + + /CX 및 WRL, 되지만 매우 권장 구성이 새 응용 프로그램에서 사용할 C + + /cli WinRT 합니다. 자세한 내용은 참조 [C + + /cli WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index)합니다.


통해 C + + /CX에서는 만들려면:

- XAML을 사용 하 여 사용자를 정의 하는 c + + 유니버설 Windows 플랫폼 (UWP) 응용 프로그램 인터페이스 및 고 네이티브 스택을 사용 합니다. 자세한 내용은 참조 [c + + (UWP)에서 "hello world" 앱 만들기](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)합니다.

- JavaScript 기반 Windows 앱에서 사용할 수 있는 c + + Windows 런타임 구성 요소입니다. 자세한 내용은 참조 [Windows 런타임 구성 요소 만들기 c + +](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)합니다.

- Windows DirectX 게임 및 그래픽 위주 앱. 자세한 내용은 참조 [DirectX로 간단한 UWP 게임을 만들](/windows/uwp/gaming/tutorial--create-your-first-metro-style-directx-game)합니다.

## <a name="related-articles"></a>관련 문서

|||
|-|-|
|[빠른 참조](../cppcx/quick-reference-c-cx.md)|테이블의 키워드 및 연산자 C + + /cli CX 합니다.|
|[형식 시스템](../cppcx/type-system-c-cx.md)|설명 기본적인 C + + /cli CX 형식 및 프로그래밍 구조체와 C + 활용 하는 방법을 + /CX를 사용 하 고 만드는 Windows 런타임 형식입니다.|
|[앱 빌드 및 라이브러리](../cppcx/building-apps-and-libraries-c-cx.md)|IDE를 사용하여 정적 라이브러리 및 DLL에 대한 링크와 응용 프로그램을 빌드하는 방법을 설명합니다.|
|[다른 언어와의 상호 운용](../cppcx/interoperating-with-other-languages-c-cx.md)|에 대해 설명 어떻게 C +를 사용 하 여 작성 된 구성 + CX를 사용할 수 있습니다 JavaScript로 작성 된 구성 요소와 모든 관리 언어에서 또는 [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)]합니다.|
|[스레딩 및 마샬링](../cppcx/threading-and-marshaling-c-cx.md)|사용자가 만든 구성 요소의 스레딩 및 마샬링 동작을 지정하는 방법을 설명합니다.|
|[네임 스페이스 참조](../cppcx/namespaces-reference-c-cx.md)|기본 네임스페이스, Platform 네임스페이스, Platform::Collections 및 관련 네임스페이스에 대한 참조 설명서입니다.|
|[유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows 런타임 앱에서 사용할 수 없는 CRT 함수를 나열합니다.|
|[Windows 10 앱에 대한 방법 가이드](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Windows 10 앱에 대한 개략적인 지침 및 자세한 정보에 대한 링크를 제공합니다.|
|[C + + /CX 파트 0 / \[n\]: 소개](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C + + /CX 파트 1 \[n\]: 간단한 클래스](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C + + /CX 파트 2 / \[n\]: 유형](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C + + /CX 파트 3 \[n\]: 작성 중](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C + + /CX 파트 4 / \[n\]: 정적 멤버 함수](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|기본적인 Visual c + + 블로그 시리즈에 C + + /cli CX 합니다.|
