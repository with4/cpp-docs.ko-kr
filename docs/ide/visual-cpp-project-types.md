---
title: "Visual c + + 프로젝트 형식 | Microsoft Docs"
ms.custom: 
ms.date: 10/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], projects
- project templates [Visual Studio], C++
- TODO comments [C++]
- projects [C++], types
- templates [C++], projects
- applications [C++], projects
- Visual C++ projects, types
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a837aa04b0e0c2b8d3d9f5cfd48181a9ea23b346
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="visual-c-project-types"></a>Visual C++ 프로젝트 형식

프로젝트 템플릿을 사용하면 만들려는 프로젝트의 종류에 적합한 기본 프로그램 구조, 메뉴, 도구 모음, 아이콘, 참조 및 `#include` 문을 만들 수 있습니다. Visual Studio는 여러 종류의 Visual C++ 프로젝트 템플릿을 포함하며 대부분의 템플릿에 대해 마법사를 제공하므로 프로젝트를 만들면서 사용자 지정할 수 있습니다. 프로젝트를 만든 후 즉시이 빌드하여 고 응용 프로그램을 실행할 수 있습니다. 응용 프로그램을 개발 하면서 간간이 빌드하는 것이 좋습니다.

프로젝트를 만드는 데 템플릿을 사용할 필요는 없지만 대부분의 경우에는 템플릿을 사용하는 것이 더 효율적입니다. 프로젝트 파일과 구조를 새로 만드는 것보다는 제공된 프로젝트 파일과 구조를 수정하는 것이 더 쉽기 때문입니다.  
  
> [!NOTE]
> C++ 프로젝트 템플릿을 사용하여 C 언어 프로젝트를 만들 수 있습니다. 생성된 프로젝트에서 파일 이름 확장명이 .cpp인 파일을 찾아 확장명을 .c로 변경합니다. 그런 다음 솔루션이 아닌 프로젝트의 **프로젝트 속성** 페이지에서 **구성 속성**, **C/C++** 를 차례로 확장하고 **고급**을 선택합니다. **컴파일 옵션** 설정을 **C 코드로 컴파일(/TC)**로 변경합니다.

## <a name="project-templates"></a>프로젝트 템플릿

Visual Studio에 포함 된 프로젝트 템플릿을 제품 버전 및 설치한 다음 작업에 따라 다릅니다. 작업의 c + + 데스크톱 개발을 설치한 경우 Visual Studio에 이러한 Visual c + + 프로젝트 템플릿이 있습니다.

### <a name="windows-desktop"></a>Windows 바탕 화면

|프로젝트 템플릿|설명|  
|----------------------|-----------------------------| 
|[Windows 콘솔 응용 프로그램](../windows/creating-a-console-application.md)|Windows 콘솔 응용 프로그램을 만들기 위한 프로젝트입니다.|
|[Windows 데스크톱 응용 프로그램](../windows/walkthrough-creating-windows-desktop-applications-cpp.md)|Windows 바탕 화면 (Win32) 응용 프로그램을 만들기 위한 프로젝트입니다.|
|[동적 연결 라이브러리](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)|동적 연결 라이브러리 (DLL) 작성용 프로젝트입니다.|
|[정적 라이브러리](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|정적 라이브러리 (LIB)를 만들기 위한 프로젝트입니다.|
|Windows 데스크톱 마법사|추가 옵션을 사용 하 여 Windows 데스크톱 응용 프로그램 및 라이브러리를 만들기 위한 마법사.|

### <a name="general"></a>일반

|프로젝트 템플릿|설명|
|----------------------|-----------------------------|
|빈 프로젝트|응용 프로그램, 라이브러리 또는 DLL을 만들기 위한 빈 프로젝트입니다. 모든 코드 또는 필요한 리소스를 추가 해야 합니다.|
|[메이크파일 프로젝트](../ide/creating-a-makefile-project.md)|외부 사용에 대 한 프로젝트 시스템을 구축 합니다.|
|공유 항목 프로젝트|여러 프로젝트 파일을 공유 하는 데 사용 되는 프로젝트입니다.|

### <a name="atl"></a>ATL

|프로젝트 템플릿|설명|
|----------------------|-----------------------------|
|[ATL 프로젝트](../atl/reference/creating-an-atl-project.md)|액티브 템플릿 라이브러리를 사용 하는 프로젝트입니다.|

### <a name="test"></a>테스트

|프로젝트 템플릿|설명|
|----------------------|-----------------------------|
|[기본 단위 테스트 프로젝트](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)|네이티브 c + + 단위 테스트를 포함 하는 프로젝트.|

### <a name="mfc"></a>MFC

MFC 및 ATL 지원 Visual Studio 설치를 구성 요소를 추가 하면 이러한 프로젝트 템플릿은 Visual Studio에 추가 됩니다.

|프로젝트 템플릿|설명|
|----------------------|-----------------------------|
|[MFC 응용 프로그램](../mfc/reference/creating-an-mfc-application.md)|Microsoft Foundation 클래스 (MFC) 라이브러리를 사용 하는 응용 프로그램을 만들기 위한 프로젝트입니다.|
|[MFC ActiveX 컨트롤](../mfc/reference/creating-an-mfc-activex-control.md)|MFC 라이브러리를 사용 하는 ActiveX 컨트롤을 만들기 위한 프로젝트입니다.|
|[MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md)|MFC 라이브러리를 사용 하는 동적 연결 라이브러리 작성용 프로젝트입니다.|

### <a name="windows-universal-apps"></a>Windows 유니버설 앱

Visual Studio 설치를 c + + Windows 유니버설 플랫폼 도구 구성 요소를 추가 하는 경우 이러한 프로젝트 템플릿은 Visual Studio에 추가 됩니다.

C + +에서 Windows 유니버설 앱의 개요를 참조 하십시오. [유니버설 Windows 앱 (c + +)](../windows/universal-windows-apps-cpp.md)합니다.

|프로젝트 템플릿|설명|
|----------------------|-----------------------------|
|새 응용 프로그램|미리 정의 된 컨트롤 또는 레이아웃이 없는 단일 페이지 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에 대 한 프로젝트입니다.|
|DirectX 11 앱|DirectX 11을 사용 하는 유니버설 Windows 플랫폼 앱 용 프로젝트입니다.|
|DirectX 12 앱|DirectX 12를 사용 하는 유니버설 Windows 플랫폼 앱 용 프로젝트입니다.|
|DirectX 11 및 XAML 앱|DirectX 11 및 XAML을 사용 하는 유니버설 Windows 플랫폼 앱 용 프로젝트입니다.|
|단위 테스트 응용 프로그램|유니버설 Windows 플랫폼 (UWP) 앱에 대 한 단위 테스트 앱을 만드는 프로젝트입니다.|
|DLL|유니버설 Windows 플랫폼 앱 또는 런타임 구성 요소에서 사용할 수 있는 네이티브 동적 연결 라이브러리 (DLL)에 대 한 프로젝트입니다.|
|정적 라이브러리|유니버설 Windows 플랫폼 앱 또는 런타임 구성 요소에서 사용할 수 있는 네이티브 정적 연결 라이브러리 (LIB)에 대 한 프로젝트입니다.|
|Windows 런타임 구성 요소|응용 프로그램 작성 된 프로그래밍 언어에 상관 없이 유니버설 Windows 플랫폼 앱에서 사용할 수 있는 Windows 런타임 구성 요소에 대 한 프로젝트입니다.|
|Windows 응용 프로그램 패키징 프로젝트|테스트용으로 로드 된 또는 Microsoft 스토어를 통해 분산 되도록 데스크톱 응용 프로그램을 활성화 하는 UWP 패키지를 만드는 프로젝트입니다.|

## <a name="todo-comments"></a>TODO 주석

프로젝트 템플릿에서 생성하는 대부분의 파일은 원하는 소스 코드를 입력할 위치를 확인할 수 있도록 TODO 주석을 포함합니다. 코드를 추가 하는 방법에 대 한 자세한 내용은 참조 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md) 및 [리소스 파일 작업](../windows/working-with-resource-files.md)합니다.

## <a name="see-also"></a>참고 항목

[응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
