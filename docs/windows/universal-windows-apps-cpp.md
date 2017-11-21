---
title: "유니버설 Windows 앱 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 656c8ac642ae9c8a6a76e1ed52ca014b5515e65f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="universal-windows-apps-c"></a>유니버설 Windows 앱(C++)
유니버설 Windows 플랫폼 (UWP) 앱은 서로 다른 장치에서 다양 한 화면 크기에 대 한 자동으로 조정 하는 콘텐츠를 중심으로 하는 간단한 사용자 인터페이스를 강조 하는 디자인 원칙을 구현 합니다. XAML 태그로 UI를 만들고 네이티브 C++에서 코드 숨김을 만듭니다. 다른 언어로 작성된 UWP 앱에서 사용할 수 있는 구성 요소(DLL)를 만들 수도 있습니다. UWP 앱에 대 한 API 화면은 다양 한 운영 체제 서비스를 제공 하는 잘 구성 된 라이브러리는 Windows 런타임에서 합니다.  

> [!TIP]  
> Windows 10 용 Windows 스토어를 통해 배포에 대 한 기존 데스크톱 응용 프로그램을 패키지 하는 데스크톱 앱 변환기를 사용할 수 있습니다. 자세한 내용은 [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project)(Centennial 프로젝트에서 Visual C++ 런타임 사용) 및 [데스크톱 브리지를 사용하여 데스크톱 앱을 UWP(유니버설 Windows 플랫폼)로 가져오기](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.
  
  
## <a name="uwp-apps-that-use-ccx"></a>C++/CX를 사용하는 UWP 앱  
  
|||  
|-|-|  
|[Visual C++ 언어 참조(C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Windows 런타임 Api의 c + + 소비를 단순화 하 고 예외 기반 오류 처리를 사용 하도록 설정 하는 확장 집합에 설명 합니다.|  
|[응용 프로그램 및 라이브러리 빌드(C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|C++/CX 앱이나 구성 요소에서 액세스할 수 있는 DLL 및 정적 라이브러리를 만드는 방법을 설명합니다.|  
|[자습서: C++를 사용하여 첫 Windows 스토어 앱 만들기](https://docs.microsoft.com/en-us/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C + +에서 유니버설 Windows 플랫폼 앱 개발의 기본 개념을 소개 하는 연습이 있습니다. (아직 Windows 10에서 UWP 개발을 위해 업데이트되지 않았습니다.)|  
|[C++로 Windows Runtime 구성 요소 만들기](https://docs.microsoft.com/en-us/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|다른 유니버설 Windows 플랫폼 앱 및 구성 요소에서 사용할 수 있는 Dll을 만드는 방법을 설명 합니다.|  
|[게임 개발](https://docs.microsoft.com/en-us/windows/uwp/gaming/)|DirectX 및 C++를 사용하여 게임을 작성하는 방법을 설명합니다.|  
  
## <a name="universal-windows-platform-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하는 유니버설 Windows 플랫폼 앱 
 Windows 런타임 c + + 템플릿 라이브러리 기준인 ISO c + + 코드가 예외 없는 환경에서 Windows 런타임 액세스할 수 있는 낮은 수준의 COM 인터페이스를 제공 합니다. 대부분의 경우에는 권장 하면 C + + 유니버설 Windows 플랫폼 앱 개발을 위한 Windows 런타임 c + + 템플릿 라이브러리 대신 CX 합니다. Windows 런타임 c + + 템플릿 라이브러리에 대 한 정보를 참조 하십시오. [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++](../visual-cpp-in-visual-studio.md)

