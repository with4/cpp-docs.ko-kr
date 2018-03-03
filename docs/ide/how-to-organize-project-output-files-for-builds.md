---
title: "방법: 빌드할 프로젝트 출력 파일 구성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, output files
- output files, organizing
ms.assetid: 521d95ea-2dcc-4da0-b5eb-ac3e57941446
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 648321c41fe02541eeb746bae24236c40dc5325e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-organize-project-output-files-for-builds"></a>방법: 빌드할 프로젝트 출력 파일 구성
이 항목에서는 프로젝트 출력 파일 구성에 대 한 모범 사례를 설명 합니다. 빌드 오류가 있습니다 프로젝트 출력 파일을 잘못 설정 하는 경우 발생할 수 있습니다. 이 항목에는 또한 각 대체 프로젝트 출력 파일을 구성 하기 위한의 장단점 간략하게 설명 합니다.  
  
## <a name="referencing-clr-assemblies"></a>CLR 어셈블리 참조  
  
#### <a name="to-reference-assemblies-with-using"></a>참조 어셈블리에 #using  
  
1.  사용자 코드에서 직접 사용 하 여 어셈블리를 참조할 수는 #using 지시문을와 같은 `#using <System.Data.dll>`합니다. 자세한 내용은 참조 [#using 지시문](../preprocessor/hash-using-directive-cpp.md)합니다.  
  
     MSIL에으로.dll,.exe,.netmodule, 또는.obj, 지정 된 파일 수 있습니다. 참조 된 구성 요소는 임의의 언어로 작성할 수 있습니다. 이 옵션을 사용 해야 합니다 Intellisense에 대 한 액세스 하므로 메타 데이터는 MSIL에서 추출 됩니다. 해당 파일에는 프로젝트;에 대 한 경로에 있어야 합니다. 그렇지 않은 경우 프로젝트가 컴파일되지 않습니다 및 Intellisense 사용할 수 없습니다. 마우스 오른쪽 단추로 클릭 하는 파일의 경로에 있는지 확인 하는 쉬운 방법을 #using 선택한는 **열려 있는 문서** 명령입니다. 파일을 찾을 수 없는 경우 알림이 표시 됩니다.  
  
     파일의 전체 경로 저장 하지 않을 경우 사용할 수 있습니다는 **/AI** 컴파일러 옵션에 대 한 검색 경로 편집 하려면 #using 참조 합니다. 자세한 내용은 [/AI(메타데이터 디렉터리 지정)](../build/reference/ai-specify-metadata-directories.md)를 참조하세요.  
  
#### <a name="to-reference-assemblies-with-fu"></a>어셈블리 /FU를 참조 하려면  
  
1.  위에서 설명한 것 처럼 코드 파일에서 직접 어셈블리를 참조 하는 대신 사용할 수는 **/FU** 컴파일러 옵션입니다. 이 방법의 장점은 별도 추가할 필요가 없습니다 #using 문 지정된 된 어셈블리를 참조 하는 모든 파일에 있습니다.  
  
     이 옵션을 설정 하려면 엽니다는 **속성 페이지** 프로젝트에 대 한 합니다. 확장 하 고는 **구성 속성** 노드를 차례로 확장 하 고는 **C/c + +** 노드 선택한 **고급**합니다. 원하는 어셈블리 옆에 추가 **강제 #using**합니다. 자세한 내용은 [/FU(강제 #using 파일 이름 지정)](../build/reference/fu-name-forced-hash-using-file.md)를 참조하세요.  
  
#### <a name="to-reference-assemblies-with-add-new-reference"></a>새 참조 추가와 어셈블리를 참조 하려면  
  
1.  이 CLR 어셈블리를 사용 하는 가장 쉬운 방법은 합니다. 첫째, 컴파일 되었는지 확인 프로젝트와는 **/clr** 컴파일러 옵션입니다. 그런 다음 프로젝트를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택 **추가**, **참조**합니다. **속성 페이지** 대화 상자가 나타납니다.  
  
2.  **속성 페이지** 대화 상자에서 **새 참조 추가**합니다. 모든.NET, COM 및 현재 프로젝트에서 사용할 수 있는 다른 어셈블리를 나열는 대화 상자가 표시 됩니다. 원하는 어셈블리를 선택 하 고 클릭 **확인**합니다.  
  
     프로젝트 참조를 설정 하면 해당 하는 종속성은 자동으로 처리 합니다. 또한 메타 데이터를 사용 하면 어셈블리의 일부인, 이므로 관리 되는 어셈블리에서 헤더 파일 또는 프로토타입 사용 되는 요소를 추가할 필요가 없습니다.  
  
## <a name="referencing-native-dlls-or-static-libraries"></a>네이티브 Dll 또는 정적 라이브러리 참조  
  
#### <a name="to-reference-native-dlls-or-static-libraries"></a>네이티브 Dll 또는 정적 라이브러리를 참조 하려면  
  
1.  적절 한 헤더 파일을 사용 하 여 코드에서 참조 된 #include 지시문입니다. 헤더 파일 include 경로 또는 현재 프로젝트의 일부 여야 합니다. 자세한 내용은 참조 [#include 지시문 (C/c + +)](../preprocessor/hash-include-directive-c-cpp.md)합니다.  
  
2.  프로젝트 종속성을 설정할 수도 있습니다. 다음 두 가지 보장 프로젝트 종속성을 설정 합니다. 먼저 프로젝트를 항상 필요한 종속 파일을 찾을 수 있도록 프로젝트에 적절 한 순서로 빌드됩니다를 확인 합니다. 둘째, 암시적으로 추가 종속 프로젝트의 출력 디렉터리 경로에 링크 타임에 파일을 쉽게 찾을 수 있도록 합니다.  
  
3.  응용 프로그램을 배포 하려면 해당 DLL을 적절 한 위치에 배치 해야 합니다. 이 다음 중 하나일 수 있습니다.  
  
    1.  실행 파일과 동일한 경로입니다.  
  
    2.  시스템 경로에 모든 위치 (의 **경로** 환경 변수).  
  
    3.  side-by-side-어셈블리입니다. 자세한 내용은 참조 [C/c + +-side-by-side 어셈블리 빌드](../build/building-c-cpp-side-by-side-assemblies.md)합니다.  
  
## <a name="working-with-multiple-projects"></a>여러 프로젝트 작업  
 기본적으로 모든 출력 파일은 프로젝트 디렉터리의 하위 디렉터리에서를 만들 프로젝트는 빌드됩니다. 빌드 구성에 따라 디렉터리의 이름은 (예: 디버그 또는 릴리스). 각 프로젝트는 형제 프로젝트는 상호 참조에서 해당 경로에 성공적으로 링크를 다른 프로젝트 출력 디렉터리를 명시적으로 추가 해야 합니다. 프로젝트 종속성을 설정할 때 자동으로 수행 됩니다. 그러나 종속성을 사용 하지 않는 경우 신중 하 게 처리 해야이 빌드를 관리 하기 매우 어려운 될 수 있으므로 합니다. 예를 들어 프로젝트 디버그 및 릴리스 구성에 형제 프로젝트의 외부 라이브러리를 포함 하는 경우 작성 중인 구성에 따라 다른 라이브러리 파일을 사용 해야 합니다. 따라서 이러한 경로 하드 코드 까다로울 수 있습니다.  
  
 모든 필수 출력 파일 (예: 실행 파일, incremental 링커 파일 및 PDB 파일)은 일반적인 솔루션 디렉터리로 복사 됩니다. 따라서 동일한 구성으로 c + + 프로젝트의 수를 포함 하는 솔루션에서 작업할 때는 모든 출력 파일은 중앙 집중화 된 간소화 된 연결 및 배포에 대 한 합니다. 응용 프로그램/라이브러리의 경우 이러한 파일을 함께 유지할 (파일은 하기 때문에 경로)를 예상 대로 작동 하는지 확인할 수 있습니다.  
  
 프로덕션 환경에 배포 하는 경우 출력 파일의 위치는 중요 한 문제를 수 있습니다. IDE에서 프로젝트를 실행 하는 동안 포함 된 라이브러리에 대 한 경로 필요가 없는 프로덕션 환경에서와 동일 합니다. 예를 들어 `#using "../../lib/debug/mylib.dll"` 그러면 코드에서 mylib.dll 다른 상대적 위치에 배포, 응용 프로그램에서 런타임 오류가 발생 합니다. 상대 경로 사용 하지 않아야이 방지 하려면 #include 문을 코드의 합니다. 하는 것이 필요한 파일이 프로젝트 빌드 경로에 있는지 확인 하 고 마찬가지로 해당 프로덕션 파일이 제대로 배치 됩니다.  
  
#### <a name="how-to-specify-where-output-files-go"></a>출력 파일의 위치를 지정 하는 방법  
  
1.  프로젝트의 위치 설정은 있습니다 프로젝트의 출력 **속성 페이지**합니다. 노드 옆에 확장 **구성 속성** 선택 **일반**합니다. 출력 위치 옆에 지정 되어 **출력 디렉터리**합니다. 자세한 내용은 참조 [일반 속성 페이지 (프로젝트)](../ide/general-property-page-project.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트 형식](../ide/visual-cpp-project-types.md)