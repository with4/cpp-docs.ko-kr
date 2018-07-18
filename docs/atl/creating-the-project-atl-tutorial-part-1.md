---
title: 프로젝트 만들기 (ATL 자습서, 1 부) | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1906ac1ae8c1e526d78690e131a7ca5147283d76
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025928"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>프로젝트 만들기(ATL 자습서, 1부)
이 자습서에서는 다각형을 표시하는 ActiveX 개체를 생성하는 비-어트리뷰트 ATL 프로젝트를 단계별로 안내합니다. 생성된 개체는 사용자가 다각형을 구성하는 변의 수를 바꾸고 화면을 새로 고치는 코드가 가능한 옵션을 포함합니다.  
  
> [!NOTE]
>  일반적으로 ATL 및 MFC는 Visual Studio의 Express 버전에서는 지원 되지 않습니다.  
  
> [!NOTE]
>  이 자습서에서는 다각형 샘플과 동일한 소스 코드를 만듭니다. 소스 코드를 수동으로 입력하지 않을 경우 [다각형 샘플 요약](../visual-cpp-samples.md)에서 다운로드 할 수 있습니다. 자습서를 통해 작업 하거나 자신의 프로젝트에 오류가 있는지 확인하는데 다각형 소스 코드를 참조할 수 있습니다.  
  
### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL 프로젝트 마법사를 사용 하 여 초기 ATL 프로젝트를 만들려면  
  
1.  Visual Studio 개발 환경의 **파일** 메뉴에서 **새로만들기**를 클릭하고 차례로 **프로젝트**를 클릭합니다.  
  
2.  **Visual C++ 프로젝트** 폴더를 클릭하고 **ATL 프로젝트**를 선택합니다.  
  
3.  형식 *다각형* 프로젝트 이름으로 합니다.  
  
     소스 코드에 대한 위치는 일반적으로 My Documents\Visual Studio Project를 기본값으로 사용하며 새 폴더가 자동으로 생성됩니다.  
  
4.  **확인**을 클릭하면 ATL 프로젝트 마법사가 열립니다.  
  
5.  **응용 프로그램 설정**을 클릭하면 사용할 수 있는 옵션이 표시됩니다.  
  
6.  컨트롤을 만들 때 컨트롤은 in-process 서버여야 합니다. **응용 프로그램 종류**는 DLL로 그대로 합니다.  
  
7.  다른 옵션의 기본값을 그대로 사용하고 **마침**을 클릭합니다.  
  
 ATL 프로젝트 마법사는 여러 개의 파일을 생성하여 프로젝트를 만듭니다. 솔루션 탐색기에서 다각형 개체를 확장하여 이러한 파일들을 볼 수 있습니다. 파일은 다음과 같습니다.  
  
    |파일|설명|  
    |----------|-----------------|  
    |Polygon.cpp|`DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer` 및 `DllUnregisterServer`의 구현이 포함되어 있습니다. 프로젝트의 ATL 개체의 목록인 개체 맵의 포함 됩니다. 이 옵션은 처음에 비어 있습니다.|  
    |Polygon.def|이 모듈 정의 파일은 링커에게 DLL에서 필요로 하는 내보내기에 대한 정보를 제공합니다.|  
    |마우스 오른쪽 단추로 Polygon.idl|인터페이스 정의 언어 파일입니다. 개체에 특정 인터페이스를 설명합니다.|  
    |Polygon.rgs|이 레지스트리 스크립트를 사용하면 프로그램의 DLL 등록을 위한 정보가 있습니다.|  
    |Polygon.rc|버전 정보 및 프로젝트 이름이 문자열로 포함된 리소스 파일입니다.|  
    |Resource.h|리소스 파일용 헤더 파일.|  
    |Polygonps.def|이 모듈 정의 파일은 경계를 넘어 호출하는 프록시와 스텁 코드에서 필요한 내보내기 정보를 링커에 제공합니다.|  
    |stdafx.cpp|`#include`되는 ATL의 헤더 파일입니다.|  
    |stdafx.h|`#include`되는 ATL의 구현 파일입니다.|  
  
1.  솔루션 탐색기에서 마우스 오른쪽 단추로 `Polygon` 프로젝트를 클릭합니다.  
  
2.  바로 가기 메뉴의 **속성**을 클릭합니다.
  
  
3.  **링커**를 클릭합니다. **Pre-UserRedirection** 옵션을 **예**로 변경합니다.  
  
4.  **확인**을 클릭합니다.  
  
 다음 단계에서는 프로젝트에 컨트롤을 추가합니다.  
  
 [2 단계로 이동 합니다.](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

