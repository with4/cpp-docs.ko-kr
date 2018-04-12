---
title: "프로젝트 (ATL 자습서, 1부) 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a9a5fc9a0d2175a419bbc0fb1aacbc9ea25006c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>프로젝트 만들기(ATL 자습서, 1부)
이 자습서에서는 다각형을 표시 하는 ActiveX 개체를 생성하는 비-어트리뷰트 ATL 프로젝트를 단계별로 안내 합니다. 생성된 개체는 사용자가 다각형을 구성하는 변의 수를 바꾸고 화면을 새로 고치는 코드가 가능한 옵션을 포함 합니다.  
  
> [!NOTE]
>  일반적으로 ATL 및 MFC는 Visual Studio의 Express 버전에서는 지원 되지 않습니다.  
  
> [!NOTE]
>  이 자습서에서는 다각형 샘플과 동일한 소스 코드를 만듭니다. 소스 코드를 수동으로 입력 하지 않을 경우 [다각형 샘플 요약](../visual-cpp-samples.md)에서 다운로드 할 수 있습니다. 자습서를 통해 작업 하거나 자신의 프로젝트에 오류가 있는지 확인 하는데 다각형 소스 코드를 참조할 수 있습니다.  
  
### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL 프로젝트 마법사를 사용 하여 초기 ATL 프로젝트를 만들려면  
  
1.  Visual Studio 개발 환경의 **파일** 메뉴에서 **새로만들기**를 클릭하고 차례로 **프로젝트**를 클릭 합니다.  
  
2.  **Visual C++ 프로젝트** 폴더를 클릭하고 **ATL 프로젝트**를 선택합니다.  
  
3.  `Polygon`을 프로젝트 이름으로 입력합니다.
  
     소스 코드에 대한 위치는 일반적으로 My Documents\Visual Studio Project가 기본값으로 사용되고 새 폴더가 자동으로 생성 됩니다.  
  
4.  **확인**을 클릭하면 ATL 프로젝트 마법사가 열립니다.  
  
5.  사용할 수 있는 옵션을 보기 위해 **응용 프로그램 설정**을 클릭합니다.
  
6.  컨트롤을 만들 때 컨트롤은 in-process 서버 여야 합니다. **응용 프로그램 종류**는 DLL로 그대로 합니다.
  
7.  다른 옵션의 기본값을 그대로 사용 하고 **마침**을 클릭 합니다.  
  
 ATL 프로젝트 마법사는 여러 개의 파일을 생성 하여 프로젝트를 만듭니다. 솔루션 탐색기에서 다각형 개체를 확장 하여 이러한 파일들을 볼 수 있습니다. 파일은 다음과 같습니다.  
  
|파일|설명|  
|----------|-----------------|  
|Polygon.cpp|`DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`, 및 `DllUnregisterServer`의 구현이 포함되어 있습니다. 또한 프로젝트에서 ATL 개체의 목록인 개체 맵을 포함 합니다. 이 옵션은 처음 비어 있습니다.|  
|Polygon.def|이 모듈 정의 파일은 링커에게 DLL에서 필요로 하는 내보내기에 대한 정보를 제공 합니다.|  
|Polygon.idl|인터페이스 정의 언어 파일입니다. 개체에 특정 인터페이스를 설명 합니다.|  
|Polygon.rgs|이 레지스트리 스크립트를 사용하면 프로그램의 DLL을 등록 하기위한 정보가 있습니다.|  
|Polygon.rc|초기 버전 정보 및 프로젝트 이름이 문자열로 포함된 리소스 파일입니다.|  
|Resource.h|리소스 파일에 대한 헤더 파일입니다.|  
|Polygonps.def|이 모듈 정의 파일은 경계를 넘어 호출하는 프록시와 스텁 코드에서 필요한 내보내기 정보를 링커에 제공합니다.
|stdafx.cpp|`#include`되는 ATL의 구현 파일입니다.|  
|stdafx.h|`#include`되는 ATL의 헤더 파일입니다.|  
  
1.  솔루션 탐색기에서 마우스 오른쪽 단추로 `Polygon` 프로젝트를 클릭합니다.
  
2.  바로 가기 메뉴의 **속성**을 클릭 합니다.  
  
3.  **링커**를 클릭 합니다. **Pre-UserRedirection** 옵션을 **예**로 변경 합니다.  
  
4.  **확인**을 클릭합니다.  
  
 다음 단계에서는 프로젝트에는 컨트롤 추가 합니다.  
  
 [2 단계로](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

