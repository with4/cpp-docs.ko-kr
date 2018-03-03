---
title: "컨트롤 (ATL 자습서, 2 부) 추가 | Microsoft Docs"
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
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aed69a5dd421e967e1da33bb3a2f2c41fa80698d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>컨트롤 추가(ATL 자습서, 2부)
이 단계에서는 프로젝트에 컨트롤을 추가를 빌드하고 웹 페이지에서 테스트 합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-add-an-object-to-an-atl-project"></a>ATL 프로젝트에 개체를 추가 하려면  
  
1.  클래스 뷰에서 다각형 프로젝트를 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  가리킨 **추가** 를 바로 가기 메뉴를 클릭 한 **클래스** 하위 메뉴에 있습니다.  
  
     **클래스 추가** 대화 상자가 나타납니다. 왼쪽의 트리 구조에 다른 개체 범주 나열 됩니다.  
  
3.  클릭는 **ATL** 폴더입니다.  
  
4.  오른쪽의 템플릿 목록에서 선택 **ATL 컨트롤**합니다. **추가**를 클릭합니다. ATL 컨트롤 마법사가 열리고 컨트롤을 구성할 수 있습니다.  
  
5.  형식 `PolyCtl` 짧은 이름 및 참고 다른 필드는 자동으로 완료 합니다. 클릭 하지 마십시오 **마침** 아직 일부 변경 해야 하기 때문에 있습니다.  
  
 ATL 컨트롤 마법사의 **이름** 페이지에는 다음 필드가 포함 됩니다.  
  
|필드|목차|  
|-----------|--------------|  
|**짧은 이름**|컨트롤에 입력 한 이름입니다.|  
|**클래스**|컨트롤을 구현 하기 위해 만든 c + + 클래스 이름입니다.|  
|**.h 파일**|C + + 클래스의 정의 포함 하기 위해 만들어진 파일입니다.|  
|**.cpp 파일**|C + + 클래스의 구현에 포함 하기 위해 만들어진 파일입니다.|  
|**CoClass**|이 컨트롤에 대 한 구성 요소 클래스의 이름입니다.|  
|**Interface**|컨트롤의 사용자 지정 메서드 및 속성 구현 됩니다 하는 인터페이스의 이름입니다.|  
|**Type**|컨트롤에 대 한 설명입니다.|  
|**ProgID**|컨트롤의 CLSID를 찾는 데 사용할 수 있는 읽을 수 있는 이름입니다.|  
  
 ATL 컨트롤 마법사에서 몇 가지 추가 설정을 확인 해야 합니다.  
  
#### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>자세한 오류 정보 및 연결 지점에 대 한 지원을 사용 하도록 설정  
  
1.  클릭 **옵션** 열려는 **옵션** 페이지.  
  
2.  선택 된 **연결점** 확인란 합니다. 이렇게 하면 송신 인터페이스에 대 한 지원을 IDL 파일에서 만들어집니다.  
  
 또한 Excel 또는 Word와 같은 포함 된 개체를 지 원하는 응용 프로그램에 포함 될 수도 즉 삽입 가능, 컨트롤을 만들 수 있습니다.  
  
#### <a name="to-make-the-control-insertable"></a>컨트롤 삽입 가능 하도록  
  
1.  클릭 **모양** 열려는 **모양** 페이지.  
  
2.  선택 된 **삽입 가능** 확인란 합니다.  
  
 개체에서 표시 하는 다각형을 추가 해야 하므로 단색 채우기 색 갖습니다는 `Fill Color` 스톡 속성입니다.  
  
#### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>채우기 색 스톡 속성을 추가 하 고 컨트롤을 만들려면  
  
1.  클릭 **스톡 속성** 열려는 **스톡 속성** 페이지.  
  
2.  아래 **지원 되지 않습니다**, 가능한 스톡 속성 목록 아래로 스크롤합니다. 두 번 클릭 `Fill Color` 로 이동 하는 **Supported** 목록입니다.  
  
3.  컨트롤에 대 한 옵션을 완료합니다. **마침**을 클릭합니다.  
  
 마법사 컨트롤을 만들 때 몇 가지 코드 변경 내용 및 파일 추가 발생 했습니다. 다음 파일을 만들었습니다.  
  
|파일|설명|  
|----------|-----------------|  
|PolyCtl.h|대부분의 c + + 클래스의 구현 포함 `CPolyCtl`합니다.|  
|PolyCtl.cpp|나머지 부분은 포함 `CPolyCtl`합니다.|  
|PolyCtl.rgs|컨트롤을 등록 하는 데 사용 하는 레지스트리 스크립트를 포함 하는 텍스트 파일입니다.|  
|PolyCtl.htm|새로 만든된 컨트롤에 대 한 참조를 포함 하는 웹 페이지입니다.|  
  
 마법사는 또한 다음 코드 변경 내용을 수행:  
  
-   추가 `#include` 문을 ATL 포함 하도록 stdafx.h 및 stdafx.cpp 파일에 컨트롤을 지 원하는 데 필요한 파일입니다.  
  
-   새 컨트롤의 세부 정보를 포함 하려면 마우스 오른쪽 단추로 변경 된 Polygon.idl 합니다.  
  
-   새 컨트롤 개체 드에서를 맵에 Polygon.cpp 성공적으로 추가 합니다.  
  
 이제 작동을 확인 하도록 컨트롤을 작성할 수 있습니다.  
  
## <a name="building-and-testing-the-control"></a>빌드 및 컨트롤 테스트  
  
#### <a name="to-build-and-test-the-control"></a>컨트롤을 빌드하고 테스트하려면  
  
1.  에 **빌드** 메뉴를 클릭 하 여 **빌드 다각형**합니다.  
  
     컨트롤 빌드를 완료 한 후에 PolyCtl.htm 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **브라우저에서 보기**합니다. 컨트롤을 포함 하는 HTML 웹 페이지 표시 됩니다. "PolyCtl 개체에 대 한 ATL 8.0 테스트 페이지" 제목 및 텍스트와 페이지가 표시 되어야 **PolyCtl**합니다. 컨트롤입니다.  
  
> [!NOTE]
>  이 자습서를 DLL 파일을 만들 수 없는 오류 메시지가 표시 되 면 완료 PolyCtl.htm 파일 및 ActiveX Control Test container 닫고 솔루션을 다시 빌드하십시오. 그래도 DLL을 만들 수 없는 컴퓨터를 다시 부팅 하거나 (터미널 서비스를 사용 하는 경우) 하는 경우 로그 오프 합니다.  
  
 다음으로, 컨트롤에는 사용자 지정 속성을 추가 합니다.  
  
 [1 단계를 다시](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [3 단계로](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

