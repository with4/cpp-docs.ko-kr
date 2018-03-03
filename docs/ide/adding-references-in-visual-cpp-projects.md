---
title: "Visual c + + 프로젝트에서 참조를 추가 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.References
dev_langs:
- C++
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7bacb5663d8e06ee5a10629c547de6f96219697e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-references-in-visual-c-projects"></a>Visual C++ 프로젝트에서 참조 추가
프로그램은 매우 일반적으로 DLL, Windows 런타임 구성 요소, 확장 SDK, COM 구성 요소 및 .NET 어셈블리와 같은 다른 이진 파일에서 API를 호출합니다. 프로그램에서 이러한 다른 이진 파일을 찾는 방식은 프로젝트의 형식 및 이진 파일의 형식에 따라 달라집니다.  
  
 네이티브 C++ 프로젝트에서 솔루션의 다른 프로젝트에 의해 생성되지 않는 네이티브 DLL이나 COM 구성 요소를 사용하고 있는 경우 LoadLibrary 또는 CoCreateInstance를 사용하여 이진 파일에 대한 경로를 지정하거나 시스템에서 잘 정의된 특정 위치를 검색하여 경로를 찾도록 합니다.  
  
 UWP 프로젝트 또는 C++/CLI 프로젝트 같은 다른 형식의 프로젝트에서 또는 이진 파일이 솔루션의 다른 프로젝트에 의해 생성되는 경우 어셈블리, 구성 요소 또는 프로젝트에 대한 *참조* 를 추가합니다.   참조는 기본적으로 프로그램에서 이진 파일을 찾아 통신할 수 있도록 하는 데이터의 집합입니다.       참조를 추가하면 Visual Studio에서 낮은 수준의 세부 정보를 처리합니다. .NET Frameworkassemblies를 c + + 프로젝트에서 참조를 설정 하려면 (C + + /CLI만), COM 구성 요소를 포함 한 솔루션의 다른 프로젝트 공유, 프로젝트 또는 연결 된 서비스 마우스 오른쪽 단추로 클릭는 **참조** 노드에서**솔루션 탐색기** 불러오는 **참조 관리자**합니다. 참조 관리자에 표시되는 항목은 프로젝트 형식에 따라 달라집니다.  
  
 네이티브 C++ 프로젝트(ATL)에서는 *참조* 의 개념이 공유 프로젝트를 포함한 솔루션의 다른 프로젝트에만 적용되어 **참조 관리자**만 표시되도록 합니다.  
  
 ![Visual C# 43; &#43; 참조 관리자 &#40; ATL 프로젝트 &#41; ] (../ide/media/visual-c---reference-manager--atl-projects-.png "Visual c + + 참조 관리자 (ATL 프로젝트)")  
  
 C++/CLI 또는 유니버설 Windows 플랫폼 프로젝트에서는 참조의 개념이 솔루션의 다른 프로젝트뿐만 아니라 더 많은 종류의 이진 파일에 적용됩니다.  이러한 참조가 모두 **참조 관리자**를 표시합니다.
  
## <a name="reference-properties"></a>참조 속성  
 각 종류의 참조에는 속성이 있습니다. 속성은 솔루션 탐색기에서 참조를 선택하고 **Alt+Enter**를 누르거나 마우스 오른쪽 단추를 클릭하고 **속성**을 선택하여 볼 수 있습니다. 일부 속성은 읽기 전용이며 일부는 수정할 수 있습니다. 그러나 일반적으로 이러한 속성은 수정할 필요가 없습니다.  
  
### <a name="activex-reference-properties"></a>ActiveX 참조 속성  
 ActiveX 참조 속성은 COM 구성 요소에 대한 참조에만 사용할 수 있습니다. **참조** 창에서 COM 구성 요소를 선택한 경우에만 이러한 속성이 표시됩니다. 이러한 속성은 수정할 수 없습니다.  
  
 **컨트롤 전체 경로**  
 참조된 컨트롤의 디렉터리 경로를 표시합니다.  
  
 **컨트롤 GUID**  
 ActiveX 컨트롤에 대한 GUID를 표시합니다.  
  
 **컨트롤 버전**  
 참조된 ActiveX 컨트롤의 버전을 표시합니다.  
  
 **형식 라이브러리 이름**  
 참조된 형식 라이브러리의 이름을 표시합니다.  
  
 **래퍼 도구**  
 참조된 COM 라이브러리 또는 ActiveX 컨트롤에서 interop 어셈블리를 빌드하는 데 사용되는 도구를 표시합니다.  
  
### <a name="assembly-reference-properties"></a>어셈블리 참조 속성  
 어셈블리 참조 속성은 C + Frameworkassemblies.NET에 대 한 참조에만 사용할 수 + /CLI 프로젝트. .NET Frameworkassembly를 선택한 경우에 이러한 속성이 표시 됩니다는 **참조** 창. 이러한 속성은 수정할 수 없습니다.  
  
 **상대 경로**  
 참조된 어셈블리에 대한 프로젝트 디렉터리의 상대 경로를 표시합니다.  
  
### <a name="build-properties"></a>빌드 속성  
 다음 속성은 다양한 종류의 참조에서 사용할 수 있습니다. 이러한 속성을 사용하면 참조로 빌드하는 방법을 지정할 수 있습니다.  
  
 **로컬 복사**  
 빌드 중 대상 위치에 대해 참조되는 어셈블리를 자동으로 복사할지 지정합니다.  
  
 **로컬 위성 어셈블리 복사**  
 참조된 어셈블리의 위성 어셈블리를 빌드 중에 대상 위치에 자동으로 복사할지 지정합니다. **로컬 복사** 가 `true`인 경우에만 사용됩니다.  
  
 **참조 어셈블리 출력**  
 이 어셈블리가 빌드 프로세스에서 사용되도록 지정합니다. `true`이면 빌드 중 어셈블리가 컴파일러 명령줄에서 사용됩니다.  
  
### <a name="project-to-project-reference-properties"></a>프로젝트 간 참조 속성  
 다음 속성은 *참조* 창에서 선택한 프로젝트와 동일한 솔루션의 다른 프로젝트 간에 **프로젝트 간 참조** 를 정의합니다. 자세한 내용은 [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)를 참조하세요.  
  
 **라이브러리 종속성 링크**  
 이 속성이 **True**이면 독립 프로젝트에서 생성한 .lib 파일인 종속 프로젝트에 프로젝트 시스템이 연결됩니다. 일반적으로 **True**를 지정합니다.  
  
 **프로젝트 식별자**  
 독립 프로젝트를 고유하게 식별합니다. 속성 값은 수정할 수 없는 내부 시스템 GUID입니다.  
  
 **라이브러리 종속성 입력 사용**  
 이 속성이 **False**이면 프로젝트 시스템이 종속 프로젝트에서 생성한 라이브러리에 대한 .obj 파일인 종속 프로젝트에 연결되지 않습니다. 따라서 이 값은 증분 링크를 해제합니다. 일반적으로 독립 프로젝트가 많은 경우 응용 프로그램을 빌드하는 데 시간이 오래 걸릴 수 있으므로 **False** 를 지정합니다.  
  
### <a name="reference-properties"></a>참조 속성  
 다음 속성은 COM 및 .NET 어셈블리 참조에 있으며 수정할 수 없습니다.  
  
 **어셈블리 이름**  
 참조된 어셈블리에 대한 어셈블리 이름을 표시합니다.  
  
 **문화권**  
 선택한 참조의 문화권을 표시합니다.  
  
 **설명**  
 선택한 참조에 대한 설명을 표시합니다.  
  
 **전체 경로**  
 참조된 어셈블리의 디렉터리 경로를 표시합니다.  
  
 **ID**  
 .NET Frameworkassemblies에 대 한 전체 경로 표시합니다. COM 구성 요소의 경우 GUID를 표시합니다.  
  
 **레이블**  
 참조의 레이블을 표시합니다.  
  
 **이름**  
 참조 이름을 표시합니다.  
  
 **공개 키 토큰**  
 참조된 어셈블리를 식별하는 데 사용되는 공개 키 토큰을 표시합니다.  
  
 **강력한 이름**  
 참조된 어셈블리에 강력한 이름이 있는 경우 `true`입니다. 강력한 이름이 지정된 어셈블리의 버전은 고유합니다.  
  
 **Version**  
 참조된 어셈블리의 버전을 표시합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)   
 [프로젝트 속성 사용](../ide/working-with-project-properties.md)