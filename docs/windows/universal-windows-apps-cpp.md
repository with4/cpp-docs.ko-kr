---
title: "유니버설 Windows 앱(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 유니버설 Windows 앱(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

UWP\(유니버설 Windows 플랫폼\) 앱은 서로 다른 장치에서 다양한 화면 크기에 맞게 자동으로 조정되는 콘텐츠를 중심으로 하는 간단한 사용자 인터페이스를 강조하는 일련의 디자인 원칙을 구현합니다. XAML 태그로 UI를 만들고 네이티브 C\+\+에서 코드 숨김을 만듭니다. 다른 언어로 작성된 UWP 앱에서 사용할 수 있는 구성 요소\(DLL\)를 만들 수도 있습니다. UWP 앱에 대한 API 화면은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]이며, 이는 다양한 운영 체제 서비스를 제공하는 잘 구성된 라이브러리입니다.  
  
> [!NOTE]
>  C\+\+의 UWP 앱 개발에 대한 대부분의 설명서는 [Windows 개발자 센터](http://go.microsoft.com/fwlink/p/?LinkId=255563) 웹 사이트에 있습니다. 이 문서의 링크 중 일부는 해당 웹 사이트로 이동합니다.  
  
## C\+\+\/CX를 사용하는 UWP 앱  
  
|||  
|-|-|  
|[Visual C\+\+ 언어 참조\(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=255561)|[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] API의 C\+\+ 소비를 단순화하고 예외 기반 오류 처리를 가능하게 하는 일련의 확장에 대해 설명합니다.|  
|[응용 프로그램 및 라이브러리 빌드\(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=264858)|C\+\+\/CX 앱이나 구성 요소에서 액세스할 수 있는 DLL 및 정적 라이브러리를 만드는 방법을 설명합니다.|  
|[자습서: C\+\+를 사용하여 첫 Windows 스토어 앱 만들기](http://go.microsoft.com/fwlink/p/?LinkId=255556)|C\+\+로 작성한 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱 개발에 대한 기본 개념을 소개하는 연습입니다. \(아직 Windows 10에서 UWP 개발을 위해 업데이트되지 않았습니다.\)|  
|[C\+\+로 작성한 Windows 스토어 앱용 로드맵](http://go.microsoft.com/fwlink/p/?LinkId=255553)|C\+\+로 작성한 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱 및 게임 개발에 대한 문서 링크를 제공합니다.|  
|[C\+\+로 Windows Runtime 구성 요소 만들기](http://go.microsoft.com/fwlink/p/?LinkId=255559)|다른 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱 및 구성 요소가 소비할 수 있는 DLL을 만드는 방법을 설명합니다.|  
|[게임 개발](http://go.microsoft.com/fwlink/p/?LinkId=255554)|DirectX 및 C\+\+를 사용하여 게임을 작성하는 방법을 설명합니다.|  
  
## [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\([!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)]\)을 사용하는 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 앱  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]에서는 ISO C\+\+ 코드가 예외 없는 환경에서 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에 액세스할 수 있는 낮은 수준의 COM 인터페이스를 제공합니다. 대부분의 경우 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 앱 개발에 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 대신 C\+\+\/CX를 사용하는 것이 좋습니다.[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]에 대한 자세한 내용은 [Windows 런타임 C\+\+ 템플릿 라이브러리\(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)를 참조하세요.  
  
## 참고 항목  
 [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)