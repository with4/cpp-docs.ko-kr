---
title: "연습: WRL 및 Media Foundation을 사용 하 여 Windows 스토어 앱 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25cc08c22ac0d33945a73744a0be6045971d9330
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation"></a>연습: WRL 및 Media Foundation을 사용하여 Windows 스토어 앱 만들기
사용 하는 유니버설 Windows 플랫폼 앱을 만들려면 Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하는 방법에 알아봅니다 [Microsoft 미디어 파운데이션](http://msdn.microsoft.com/library/windows/apps/ms694197)합니다.  
  
 이 예제에서는 웹캠에서 캡처된 이미지에 회색조 효과를 적용하는 사용자 지정 Media Foundation 변형을 만듭니다. 앱에서는 C++를 사용하여 사용자 지정 변환을 정의하고, C#을 사용하여 구성 요소를 통해 캡처된 이미지를 변환합니다.  
  
> [!NOTE]
>  C# 대신 JavaScript, Visual Basic 또는 C++를 사용하여 사용자 지정 변형 구성 요소를 사용할 수도 있습니다.  
  

 대부분의 경우에서 다음을 사용할 수 있습니다 C + + /CX를 Windows 런타임 만들기). 그러나 경우에 따라 사용 해야 WRL 합니다. 예를 들어, Microsoft Media Foundation 용 미디어 확장을 만드는 경우 모두 COM 및 Windows 런타임 인터페이스를 구현 하는 구성 요소를 만들어야 합니다. 때문에 C + + /cli 미디어 확장을 만들기 위해 사용 해야 모두 COM 및 Windows 런타임 인터페이스의 구현할 수 있기 때문에 WRL 합니다 CX만 Windows 런타임 개체를 만들 수 있습니다.  

  
> [!NOTE]
>  이 코드 예제는 길지만, 유용한 Media Foundation 변형을 만드는 데 필요한 최소한의 코드를 보여 줍니다. 이를 사용자 지정 변형의 시작점으로 사용할 수 있습니다. 이 예제는에서 [미디어 확장명 샘플](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)및 디코딩하고, 미디어 스트림을 생성 하는 스키마 처리기를 만드는 비디오에 효과 적용 하려면 미디어 확장을 사용 하 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
  
-   경험이 [Windows 런타임](http://msdn.microsoft.com/library/windows/apps/br211377.aspx)합니다.  
  
-   COM 경험  
  
-   웹캠  
  
## <a name="key-points"></a>주요 사항  
  
-   사용자 지정 Media Foundation 구성 요소를 만들려면 MIDL(Microsoft Interface Definition Language) 정의 파일을 사용하여 인터페이스를 정의하고 해당 인터페이스를 구현한 후 다른 구성 요소에서 활성화할 수 있도록 합니다.  
  
-   `namespace` 및 `runtimeclass` 특성 및 `NTDDI_WIN8` [버전](http://msdn.microsoft.com/en-us/66ac5cf3-2230-44fd-aaf6-8013e4a4ae81) 특성 값은 WRL을 사용 하는 Media Foundation 구성 요소에 대 한 MIDL 정의의 중요 한 부분입니다.  
  
-   [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md) 는 사용자 지정 Media Foundation 구성 요소에 대 한 기본 클래스입니다. [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](../windows/runtimeclasstype-enumeration.md) 템플릿 인수로 제공 되는 열거형 값을 사용 하 여 Windows 런타임 클래스 및 클래식 COM 런타임 클래스 둘 다에 대 한 클래스를 표시 합니다.  
  
-   [InspectableClass](../windows/inspectableclass-macro.md) 참조 계산과 같은 기본 COM 기능을 구현 하는 매크로 및 `QueryInterface` 메서드 및 런타임 클래스 이름 및 신뢰 수준을 설정 합니다.  
  
-   microsoft:: wrl을 사용 하 여::[모듈 클래스](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/b4acf5de-2f4c-4c8b-b5ff-9140d023ecbe/locales/en-US) 와 같은 DLL 진입점 함수를 구현 하려면 [DllGetActivationFactory](http://msdn.microsoft.com/library/br205771.aspx), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368\(v=vs.85\).aspx), 및 [ DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/ms680760\(v=vs.85\).aspx)합니다.  
  
-   구성 요소 DLL을 runtimeobject.lib에 연결합니다. 또한 지정할 [/WINMD](../cppcx/compiler-and-linker-options-c-cx.md) Windows 메타 데이터를 생성 하는 링커 줄에 있습니다.  
  
-   WRL 구성 요소를 유니버설 Windows 플랫폼 앱에 액세스할 수 있도록 하려면 프로젝트 참조를 사용 합니다.  
  
### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>사용 하려면 Media Foundation 회색조 만들려는 WRL 구성 요소를 변환  
  
1.  Visual Studio에서 만듭니다는 **빈 솔루션** 프로젝트. 예를 들어 프로젝트 이름을 `MediaCapture`합니다.  
  
2.  추가 **DLL (Windows 스토어 앱)** 프로젝트를 솔루션입니다. 예를 들어 프로젝트 이름을 `GrayscaleTransform`합니다.  
  
3.  추가 **Midl 파일 (.idl)** 파일을 프로젝트입니다. 예를 들어 파일 이름을 `GrayscaleTransform.idl`합니다.  
  
4.  이 코드를 GrayscaleTransform.idl에 추가합니다.  
  
     [!code-cpp[wrl-media-capture#1](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]  
  
5.  다음 코드를 사용하여 pch.h의 내용을 바꿉니다.  
  
     [!code-cpp[wrl-media-capture#2](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]  
  
6.  프로젝트에 새 헤더 파일을 추가, 이름을 `BufferLock.h`,이 코드를 추가 합니다.  
  
     [!code-cpp[wrl-media-capture#3](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]  
  
7.  GrayscaleTransform.h는 이 예제에서 사용되지 않습니다. 원하는 경우 프로젝트에서 제거할 수 있습니다.  
  
8.  다음 코드를 사용하여 GrayscaleTransform.cpp의 내용을 바꿉니다.  
  
     [!code-cpp[wrl-media-capture#4](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]  
  
9. 새 모듈 정의 파일을 프로젝트에 추가, 이름을 `GrayscaleTransform.def`,이 코드를 추가 합니다.  
  
   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```   
  
10. 다음 코드를 사용하여 dllmain.cpp의 내용을 바꿉니다.  
  
     [!code-cpp[wrl-media-capture#6](../windows/codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]  
  
11. 프로젝트의 **속성 페이지** 대화 상자에서 다음 설정 **링커** 속성입니다.  
  
    1.  아래 **입력**에 대 한는 **모듈 정의 파일**, 지정 `GrayScaleTransform.def`합니다.  
  
    2.  또한 아래에서 **입력**, 추가 `runtimeobject.lib`, `mfuuid.lib`, 및 `mfplatf.lib` 에 **추가 종속성** 속성입니다.  
  
    3.  아래 **Windows 메타 데이터**설정, **일반 Windows 메타 데이터** 를 **예 (/ WINMD)**합니다.  
  
### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>WRL C# 응용 프로그램에서 사용자 지정 Media Foundation 구성 요소를 사용 하려면  
  
1.  새로 추가 **C# 빈 앱 (XAML)** 에 프로젝트는 `MediaCapture` 솔루션입니다. 예를 들어 프로젝트 이름을 `MediaCapture`합니다.  
  
2.  에 **MediaCapture** 프로젝트에서 추가에 대 한 참조는 `GrayscaleTransform` 프로젝트. 자세한 내용은 참조 [하는 방법: 참조 추가 또는 제거 참조 관리자를 사용 하 여](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)합니다.  
  
3.  Package.appxmanifest에서에 **기능** 탭에서 **마이크** 및 **웹캠**합니다. 두 기능 모두 웹캠에서 사진을 캡처하는 데 필요합니다.  
  
4.  MainPage.xaml에서 루트에이 코드를 추가 [그리드](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) 요소:  
  
     [!code-xml[wrl-media-capture#7](../windows/codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]  
  
5.  다음 코드를 사용하여 MainPage.xaml.cs의 내용을 바꿉니다.  
  
     [!code-cs[wrl-media-capture#8](../windows/codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]  
  
 다음 그림에서는 MediaCapture 앱을 보여 줍니다.  
  
 ![사진을 캡처하는 MediaCapture 앱](../windows/media/wrl_media_capture.png "WRL_Media_Capture")  
  
## <a name="next-steps"></a>다음 단계  
 이 예제에서는 기본 웹캠에서 한 번에 하나씩 사진을 캡처하는 방법을 보여 줍니다. [미디어 확장명 샘플](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) 많은 기능을 수행 합니다. 웹캠 장치를 열거하고 로컬 스키마 처리기를 사용하는 방법을 보여 주며, 개별 사진과 비디오 스트림 모두에서 작동하는 추가 미디어 효과를 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft 미디어 파운데이션](http://msdn.microsoft.com/library/windows/apps/ms694197)   
 [미디어 확장명 샘플](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)