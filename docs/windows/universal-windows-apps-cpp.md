---
title: 유니버설 Windows 앱 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 56b6642bb24107da4c09856dbd8daaf70fb7dfd5
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015009"
---
# <a name="universal-windows-apps-c"></a>유니버설 Windows 앱(C++)

UWP (유니버설 Windows 플랫폼) 앱은 다양 한 장치에서 다양 한 화면 크기에 대 한 자동으로 조정 하는 콘텐츠를 중심으로 하는 간단한 사용자 인터페이스를 강조 하는 디자인 원칙을 구현 합니다. XAML 태그로 UI를 만들고 네이티브 C++에서 코드 숨김을 만듭니다. 다른 언어로 작성된 UWP 앱에서 사용할 수 있는 구성 요소(DLL)를 만들 수도 있습니다. UWP 앱에 대 한 API 화면은 다양 한 운영 체제 서비스를 제공 하는 잘 구성 된 라이브러리는 Windows 런타임입니다.

> [!TIP]  
> Windows 10 용 Microsoft Store 통해 배포할 기존의 데스크톱 응용 프로그램 패키지를 데스크톱 브리지 앱 변환기를 사용할 수 있습니다. 자세한 내용은 [Centennial 프로젝트에서 사용 하 여 Visual c + + 런타임](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) 하 고 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root)합니다.

## <a name="uwp-apps-that-use-cwinrt"></a>UWP 앱을 사용 하 여 C + + /cli WinRT

C + + /cli WinRT 프로젝션인 새, 헤더 전용 라이브러리 기반 c + + 언어와 달리 C + 완전히 표준 c + +를 사용 하는 Windows 런타임용 + CX 구현 합니다. C + + /cli WinRT 비표준 구문 또는 Microsoft 언어 확장을 사용 하지 않는 및 활용 전체 c + + 컴파일러가 최적화 된 출력을 만듭니다. 자세한 내용은 [C + + /cli WinRT](/windows/uwp/cpp-and-winrt-apis)합니다. 소개 C + + /cli WinRT 및 코드 빠른 시작을 참조 하세요 [소개 C + + /cli WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)합니다.

## <a name="uwp-apps-that-use-ccx"></a>UWP 앱을 사용 하 여 C + + /cli CX

|||
|-|-|
|[Visual C++ 언어 참조(C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Windows 런타임 Api의 c + + 사용을 간소화 하 고 예외 기반 오류 처리를 사용 하도록 설정 하는 확장 집합을 설명 합니다.|
|[응용 프로그램 및 라이브러리 빌드(C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|C++/CX 앱이나 구성 요소에서 액세스할 수 있는 DLL 및 정적 라이브러리를 만드는 방법을 설명합니다.|
|[자습서: 만들기 UWP "Hello, World" 앱에서 C + + /cli CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C +의 UWP 앱 개발의 기본 개념을 소개 하는 연습은 + CX 합니다. |
|[C + Windows 런타임 구성 요소 만들기 + CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|다른 UWP 앱 및 구성 요소를 사용할 수 있는 Dll을 만드는 방법을 설명 합니다.|
|[UWP 게임 프로그래밍](/windows/uwp/gaming/)|DirectX 및 C +를 사용 하는 방법에 설명 합니다. + 게임을 만들려면 CX 합니다.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하는 UWP 앱

Windows Runtime c + + 템플릿 라이브러리는 ISO c + + 코드가 예외 없는 환경에서 Windows 런타임 액세스할 수 있는 하위 수준 COM 인터페이스를 제공 합니다. 대부분의 경우에서 것이 좋습니다를 사용 하는 C + + /cli WinRT 또는 C + + UWP 앱 개발을 위한 Windows Runtime c + + 템플릿 라이브러리 대신 CX 합니다. Windows Runtime c + + 템플릿 라이브러리에 대 한 정보를 참조 하세요 [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)합니다.

## <a name="see-also"></a>참고자료
 [Visual C++](../visual-cpp-in-visual-studio.md)<br/>