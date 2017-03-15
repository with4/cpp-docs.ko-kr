---
title: "속성 페이지(Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.NotAProp.Edit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "빌드 매크로"
  - "매크로, 프로젝트 파일"
  - "프로젝트 속성[C++], 기본값"
  - "프로젝트 속성[C++], 설정"
  - "프로젝트 파일 매크로"
  - "속성 페이지, 프로젝트 설정"
  - "사용자 정의 매크로"
  - "사용자 정의 값"
  - "Visual C++ 프로젝트, 속성"
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 속성 페이지(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

속성 페이지를 사용하여 Visual Studio 프로젝트에 대한 설정을 지정할 수 있습니다.  Visual Studio 프로젝트에 대한 **속성 페이지** 대화 상자를 열려면 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
 모든 빌드 구성을 적용하도록 프로젝트 설정을 지정하거나 각 빌드 구성에 대해 다른 프로젝트 속성을 지정할 수 있습니다.  예를 들어, 릴리스 구성에 대한 설정과 디버그 구성에 대한 다른 특정 설정을 지정할 수 있습니다.  
  
 **속성 페이지** 대화 상자에 사용 가능한 페이지가 모두 표시되는 것은 아닙니다.  표시되는 페이지는 프로젝트에서 파일 형식에 따라 다릅니다.  
  
 자세한 내용은 [프로젝트 속성 사용](../ide/working-with-project-properties.md)을 참조하세요.  
  
## 기본 속성과수정된 속성  
 **새 프로젝트** 대화 상자를 사용하여 프로젝트를 만드는 경우 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서는 지정된 프로젝트 템플릿을 사용하여 프로젝트 속성을 초기화합니다.  따라서 템플릿의 속성 값을 해당 프로젝트 형식에 대한 기본값으로 생각할 수 있습니다.  다른 프로젝트 형식에서는 속성이 다른 기본값을 가질 수 있습니다.  
  
 프로젝트 속성 값을 수정하면 굵게 표시됩니다.  프로젝트 속성은 다음과 같은 경우에 수정될 수 있습니다.  
  
-   응용 프로그램 마법사에서 프로젝트 템플릿에 지정된 값과 다른 속성 값을 필요로 하여 속성을 변경한 경우  
  
-   사용자가 **새 프로젝트** 대화 상자에서 다른 속성 값을 지정한 경우  
  
-   사용자가 프로젝트 속성 페이지에 다른 속성 값을 지정한 경우  
  
> [!TIP]
>  프로젝트를 빌드하기 위해 MSBuild를 사용하는 속성 값의 최종 집합을 확인하려면 **MSBuild \/preprocess:***preprocessor\_output\_filename*opt *project\_filename*opt 명령줄을 사용하여 생성할 수 있는 전처리기 출력 파일을 검사합니다.  
  
## 속성 다시 설정  
 프로젝트에 대해 **속성 페이지** 대화 상자를 보고 프로젝트 노드를 **솔루션 탐색기**에서 선택한 경우 대부분의 속성에서 **부모 또는 프로젝트 기본값에서 상속**을 선택하거나 값을 다른 방식으로 수정할 수 있습니다.  
  
 프로젝트에 대해 **속성 페이지** 대화 상자를 보고 파일을 **솔루션 탐색기**에서 선택한 경우 대부분의 속성에서 **부모 또는 프로젝트 기본값에서 상속**을 선택하거나 값을 다른 방식으로 수정할 수 있습니다.  그러나 프로젝트에 프로젝트 기본값과 다른 속성 값이 있는 많은 파일이 포함된 경우 프로젝트는 더 이상 빌드되지 않습니다.  
  
> [!TIP]
>  **속성 페이지** 대화 상자를 새로 고쳐 최근 선택한 내용을 표시하려면 **적용**을 클릭합니다.  
  
 대부분의 프로젝트 기본값은 시스템\(플랫폼\) 기본값입니다.  그러나 일부 프로젝트 기본값은 프로젝트에 대한 **일반** 구성 속성 페이지의 **프로젝트 기본값** 섹션에서 속성을 업데이트할 때 적용되는 스타일시트에서 파생됩니다.  자세한 내용은 [일반 속성 페이지\(프로젝트\)](../ide/general-property-page-project.md)를 참조하세요.  
  
## 사용자 정의 값 지정  
 특정 속성에 대한 값을 정의해야 합니다.  사용자 정의 값에는 하나 이상의 영숫자 문자 또는 프로젝트 파일 매크로 이름이 포함될 수 있습니다.  이러한 속성 중 일부는 하나의 사용자 정의 값만 필요로 하지만 다른 속성은 여러 값의 세미콜론으로 구분된 목록을 사용할 수 있습니다.  
  
 속성에 대한 사용자 정의 값이나 속성에서 여러 사용자 정의 값을 사용할 수 있는 경우의 목록을 속성 이름의 오른쪽 열에 지정하려면 다음 작업 중 하나를 수행합니다.  
  
-   값 또는 값 목록을 입력합니다.  
  
-   드롭다운 화살표를 클릭합니다.  **편집**을 사용할 수 있는 경우 이 항목을 클릭한 다음 텍스트 상자에서 값 또는 값 목록을 입력합니다.  목록을 지정하는 다른 방법은 텍스트 상자에서 별도의 줄에 각 값을 입력하는 것입니다.  속성 페이지에서는 값이 세미콜론으로 구분된 목록으로 표시됩니다.  
  
     프로젝트 파일 매크로를 값으로 삽입하려면 **매크로**를 클릭한 다음 매크로 이름을 두 번 클릭 합니다.  
  
-   드롭다운 화살표를 클릭합니다.  **찾아보기**를 사용할 수 있는 경우 클릭한 다음 하나 이상의 값을 선택합니다.  
  
 다중 값 속성의 경우 속성 이름 오른쪽의 열에서 드롭다운 화살표를 클릭한 다음 **편집**을 클릭하면 **부모 또는 프로젝트 기본값에서 상속** 옵션을 사용할 수 있습니다.  기본적으로 이 옵션이 선택됩니다.  
  
 속성 페이지에는 다른 수준에서 상속되는 다중 값 속성에 대해 현재 수준에서의 설정만 표시합니다.  예를 들어, **솔루션 탐색기**에서 파일이 선택한 경우 C\/C\+\+ **전처리기 정의** 속성을 선택하면 파일 수준 정의는 표시되지만 상속된 프로젝트 수준의 정의는 표시되지 않습니다.  현재 수준과 상속된 값을 모두 확인하려면 열에서 드롭다운 화살표를 속성 이름 오른쪽으로 클릭한 후 **편집**을 클릭합니다.  [Visual C\+\+ 프로젝트 모델](http://msdn.microsoft.com/ko-kr/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f)을 사용하는 경우 이 동작은 파일 및 프로젝트의 개체에도 적용됩니다.  즉, 파일 수준에서 속성에 대한 값을 쿼리할 때 프로젝트 수준에서 동일한 속성에 대한 값은 가져오지 않습니다.  프로젝트 수준에서 속성의 값을 명시적으로 가져와야 합니다.  또한 상속된 일부 속성 값은 프로그래밍 방식으로 액세스할 수 없는 스타일시트에서 가져온 값일 수 있습니다.  
  
## 단원 내용  
  
1.  [참조 검색 경로 추가 대화 상자](http://msdn.microsoft.com/ko-kr/4520d80d-aa9f-4d11-b92b-2f64a1fd5cb2)  
  
2.  [\<Projectname\> 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 고급](../ide/advanced-manifest-tool.md)  
  
3.  [명령줄 속성 페이지](../ide/command-line-property-pages.md)  
  
4.  [사용자 지정 빌드 단계 속성 페이지: 일반](../ide/custom-build-step-property-page-general.md)  
  
5.  [참조 추가](../ide/adding-references-in-visual-cpp-projects.md)  
  
6.  [일반 속성 페이지\(파일\)](../ide/general-property-page-file.md)  
  
7.  [일반 속성 페이지\(프로젝트\)](../ide/general-property-page-project.md)  
  
8.  [\<Projectname\> 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 일반](../ide/general-manifest-tool-configuration-properties.md)  
  
9. [HLSL 속성 페이지](../ide/hlsl-property-pages.md)  
  
10. [HLSL 속성 페이지: 고급](../ide/hlsl-property-pages-advanced.md)  
  
11. [HLSL 속성 페이지: 일반](../ide/hlsl-property-pages-general.md)  
  
12. [HLSL 속성 페이지: 출력 파일](../ide/hlsl-property-pages-output-files.md)  
  
13. [\<Projectname\> 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 입력 및 출력](../ide/input-and-output-manifest-tool.md)  
  
14. [\<Projectname\> 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 격리 COM](../ide/isolated-com-manifest-tool.md)  
  
15. [링커 속성 페이지](../ide/linker-property-pages.md)  
  
16. [관리되는 리소스 속성 페이지](../ide/managed-resources-property-page.md)  
  
17. [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)  
  
18. [MIDL 속성 페이지](../ide/midl-property-pages.md)  
  
19. [MIDL 속성 페이지: 고급](../ide/midl-property-pages-advanced.md)  
  
20. [MIDL 속성 페이지: 일반](../ide/midl-property-pages-general.md)  
  
21. [MIDL 속성 페이지: 출력](../ide/midl-property-pages-output.md)  
  
22. [NMake 속성 페이지](../ide/nmake-property-page.md)  
  
23. [리소스 속성 페이지](../ide/resources-property-pages.md)  
  
24. [VC\+\+ 디렉터리 속성 페이지](../ide/vcpp-directories-property-page.md)  
  
25. [웹 참조 속성 페이지](../ide/web-references-property-page.md)  
  
26. [XML 데이터 생성기 도구 속성 페이지](../ide/xml-data-generator-tool-property-page.md)  
  
27. [XML 문서 생성기 도구 속성 페이지](../ide/xml-document-generator-tool-property-pages.md)  
  
## 참고 항목  
 [방법: 프로젝트 종속성 만들기 및 제거](../Topic/How%20to:%20Create%20and%20Remove%20Project%20Dependencies.md)   
 [방법: 구성 만들기 및 편집](../Topic/How%20to:%20Create%20and%20Edit%20Configurations.md)   
 [응용 프로그램 배포](http://msdn.microsoft.com/ko-kr/4ff8881d-0daf-47e7-bfe7-774c625031b4)