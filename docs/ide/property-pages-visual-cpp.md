---
title: 속성 페이지 (Visual c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.NotAProp.Edit
dev_langs:
- C++
helpviewer_keywords:
- project-file macro
- project properties [C++], default values
- user-defined values
- project properties [C++], setting
- macros, project-file
- property pages, project settings
- Visual C++ projects, properties
- build macro
- user-defined macros
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1dc831dff6d1e3dbef4fc762712e8125a5b20e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="property-pages-visual-c"></a>속성 페이지(Visual C++)

속성 페이지를 사용하여 Visual Studio 프로젝트에 대한 설정을 지정할 수 있습니다. 열려는 **속성 페이지** 대화 상자는 Visual Studio에 대 한 프로젝트의 경우는 **프로젝트** 메뉴 선택 **속성**합니다.

모든 빌드 구성을 적용하도록 프로젝트 설정을 지정하거나 각 빌드 구성에 대해 다른 프로젝트 속성을 지정할 수 있습니다. 예를 들어, 릴리스 구성에 대한 설정과 디버그 구성에 대한 다른 특정 설정을 지정할 수 있습니다.

사용할 수 있는 모든 페이지에 반드시 표시 되는 **속성 페이지** 대화 상자. 표시되는 페이지는 프로젝트에서 파일 형식에 따라 다릅니다.

자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.

비 Windows 프로젝트에 대 한 참조 [Linux c + + 속성 페이지 참조](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->합니다.

## <a name="default-properties-vs-modified-properties"></a>기본 속성과 수정된 속성

사용 하는 경우는 **새 프로젝트** Visual Studio 프로젝트를 만들려면 대화 상자는 지정한 프로젝트 템플릿의 프로젝트 속성을 초기화를 사용 하 여 합니다. 따라서 템플릿의 속성 값을 해당 프로젝트 형식에 대한 기본값으로 생각할 수 있습니다. 다른 프로젝트 형식에서는 속성이 다른 기본값을 가질 수 있습니다.

프로젝트 속성 값을 수정하면 굵게 표시됩니다. 프로젝트 속성은 다음과 같은 경우에 수정될 수 있습니다.

- 응용 프로그램 마법사에서 프로젝트 템플릿에 지정된 값과 다른 속성 값을 필요로 하여 속성을 변경한 경우

- 다른 속성 값을 지정 된 **새 프로젝트** 대화 상자.

- 사용자가 프로젝트 속성 페이지에 다른 속성 값을 지정한 경우

> [!TIP]
> MSBuild 프로젝트 빌드를 사용 하 여 속성 값의 최종 집합을 보려면 명령줄을 사용 하 여 만들 수 있는 전처리기 출력 파일을 검토: **MSBuild 전처리 /:** *preprocessor_output_ filename*<sub>opt</sub> *project_filename*<sub>선택</sub>

## <a name="resetting-properties"></a>속성 다시 설정

볼 때의 **속성 페이지** 프로젝트 및 프로젝트 노드에 대 한 대화 상자에서 선택한 **솔루션 탐색기**, 대부분의 속성을 선택할 수 있습니다 **부모 또는 프로젝트에서 상속 기본값** 값을 수정 하거나 또 다른 방법은 합니다.

볼 때의 **속성 페이지** 프로젝트 및 파일에 대 한 대화 상자에서 선택한 **솔루션 탐색기**, 대부분의 속성을 선택할 수 있습니다 **부모또는프로젝트기본값에서상속** 값을 수정 하거나 또 다른 방법은 합니다. 그러나 프로젝트에 프로젝트 기본값과 다른 속성 값이 있는 많은 파일이 포함된 경우 프로젝트는 더 이상 빌드되지 않습니다.

> [!TIP]
> 새로 고치는 **속성 페이지** 대화 상자에서 최신 선택 사항을 표시 되도록 선택 **적용**합니다.

대부분의 프로젝트 기본값은 시스템(플랫폼) 기본값입니다. 일부 프로젝트 기본값에서 속성을 업데이트할 때 적용 되는 스타일 시트에서 파생 된 **프로젝트 기본값** 섹션은 **일반** 프로젝트에 대 한 구성 속성 페이지. 자세한 내용은 참조 [일반 속성 페이지 (프로젝트)](../ide/general-property-page-project.md)합니다.

## <a name="specifying-user-defined-values"></a>사용자 정의 값 지정

특정 속성에 대한 값을 정의해야 합니다. 사용자 정의 값에는 하나 이상의 영숫자 문자 또는 프로젝트 파일 매크로 이름이 포함될 수 있습니다. 이러한 속성 중 일부는 하나의 사용자 정의 값만 필요로 하지만 다른 속성은 여러 값의 세미콜론으로 구분된 목록을 사용할 수 있습니다.

속성에 대한 사용자 정의 값이나 속성에서 여러 사용자 정의 값을 사용할 수 있는 경우의 목록을 속성 이름의 오른쪽 열에 지정하려면 다음 작업 중 하나를 수행합니다.

- 값 또는 값 목록을 입력합니다.

- 드롭다운 화살표를 선택 합니다. 경우 **편집** 사용할 수 있는 항목을 선택 하 고 다음 텍스트 상자에 값 또는 값 목록을 입력 합니다. 목록을 지정하는 다른 방법은 텍스트 상자에서 별도의 줄에 각 값을 입력하는 것입니다. 속성 페이지에서는 값이 세미콜론으로 구분된 목록으로 표시됩니다.

   값으로 프로젝트 파일 매크로 삽입 하려면 선택 **매크로** 매크로 이름을 두 번 클릭 합니다.

- 드롭다운 화살표를 선택 합니다. 경우 **찾아보기** 사용할 수 있는 선택한 다음 하나 이상의 값을 선택 합니다.

다중값된 속성에 대 한는 **부모 또는 프로젝트 기본값에서 상속** 속성 이름의 오른쪽 열에서 드롭다운 화살표를 선택 하 고 다음 선택 옵션을 사용할 수 **편집**합니다. 기본적으로 이 옵션이 선택됩니다.

속성 페이지에는 다른 수준에서 상속되는 다중 값 속성에 대해 현재 수준에서의 설정만 표시합니다. 예를 들어에서 파일을 선택한 경우 **솔루션 탐색기** C/c + +를 선택 하 고 **전처리기 정의** 속성, 파일-수준 정의 표시 되지만 상속 프로젝트 수준의 정의 표시 되지 않습니다. 모두 현재 수준과 상속 된 값을 볼 속성 이름의 오른쪽 열에서 드롭다운 화살표를 선택 하 고 선택 합니다 **편집**합니다. 사용 하는 경우는 [Visual c + + 프로젝트 모델](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine),이 동작은 또한 파일 및 프로젝트에는 개체에 대 한 영향입니다. 즉, 파일 수준에서 속성에 대한 값을 쿼리할 때 프로젝트 수준에서 동일한 속성에 대한 값은 가져오지 않습니다. 프로젝트 수준에서 속성의 값을 명시적으로 가져와야 합니다. 또한 상속된 일부 속성 값은 프로그래밍 방식으로 액세스할 수 없는 스타일시트에서 가져온 값일 수 있습니다.

## <a name="in-this-section"></a>섹션 내용

[구성 속성, 매니페스트 도구, 고급 \<프로젝트 이름 > 속성 페이지 대화 상자](../ide/advanced-manifest-tool.md)

[명령줄 속성 페이지](../ide/command-line-property-pages.md)

[사용자 지정 빌드 단계 속성 페이지: 일반](../ide/custom-build-step-property-page-general.md)

[참조 추가](../ide/adding-references-in-visual-cpp-projects.md)

[일반 속성 페이지(파일)](../ide/general-property-page-file.md)

[일반 속성 페이지(프로젝트)](../ide/general-property-page-project.md)

[일반, 매니페스트 도구, 구성 속성, \<프로젝트 이름 > 속성 페이지 대화 상자](../ide/general-manifest-tool-configuration-properties.md)

[HLSL 속성 페이지](../ide/hlsl-property-pages.md)

[HLSL 속성 페이지: 고급](../ide/hlsl-property-pages-advanced.md)

[HLSL 속성 페이지: 일반](../ide/hlsl-property-pages-general.md)

[HLSL 속성 페이지: 출력 파일](../ide/hlsl-property-pages-output-files.md)

[입력 및 출력, 매니페스트 도구, 구성 속성, \<프로젝트 이름 > 속성 페이지 대화 상자](../ide/input-and-output-manifest-tool.md)

[구성 속성, 매니페스트 도구, COM 격리 \<프로젝트 이름 > 속성 페이지 대화 상자](../ide/isolated-com-manifest-tool.md)

[링커 속성 페이지](../ide/linker-property-pages.md)

[관리되는 리소스 속성 페이지](../ide/managed-resources-property-page.md)

[매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)

[MIDL 속성 페이지](../ide/midl-property-pages.md)

[MIDL 속성 페이지: 고급](../ide/midl-property-pages-advanced.md)

[MIDL 속성 페이지: 일반](../ide/midl-property-pages-general.md)

[MIDL 속성 페이지: 출력](../ide/midl-property-pages-output.md)

[NMake 속성 페이지](../ide/nmake-property-page.md)

[리소스 속성 페이지](../ide/resources-property-pages.md)

[VC++ 디렉터리 속성 페이지](../ide/vcpp-directories-property-page.md)

[웹 참조 속성 페이지](../ide/web-references-property-page.md)

[XML 데이터 생성기 도구 속성 페이지](../ide/xml-data-generator-tool-property-page.md)

[XML 문서 생성기 도구 속성 페이지](../ide/xml-document-generator-tool-property-pages.md)

## <a name="see-also"></a>참고자료

[방법: 프로젝트 종속성 만들기 및 제거](/visualstudio/ide/how-to-create-and-remove-project-dependencies)  
[방법: 구성 만들기 및 편집](/visualstudio/ide/how-to-create-and-edit-configurations)  
