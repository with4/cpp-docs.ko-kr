---
title: "프로젝트 (ATL 자습서, 1 부) 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a9a5fc9a0d2175a419bbc0fb1aacbc9ea25006c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>프로젝트 만들기(ATL 자습서, 1부)
이 자습서에서는 다각형을 표시 하는 ActiveX 개체를 생성 하지 않는 ATL 프로젝트를 단계별로 합니다. 개체는 화면을 새로 고치려면 다각형, 및 코드를 구성 하는 양쪽의 수를 변경 하 고 사용자에 대 한 옵션을 포함 합니다.  
  
> [!NOTE]
>  ATL 및 MFC는 일반적으로 Visual Studio의 Express 버전에서는 지원 되지 않습니다.  
  
> [!NOTE]
>  이 자습서에서는 다각형 샘플과 동일한 소스 코드를 만듭니다. 소스 코드를 수동으로 입력 하지 않으려는 경우에서 다운로드할 수 있습니다는 [다각형 샘플 추상](../visual-cpp-samples.md)합니다. 자습서를 통해 작업 하거나 사용자 고유의 프로젝트에 오류가 있는지 확인 하는 데 사용할 다각형 소스 코드를 참조할 수 있습니다.  
  
### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL 프로젝트 마법사를 사용 하 여 초기 ATL 프로젝트를 만들려면  
  
1.  Visual Studio 개발 환경에서 클릭 **새로** 에 **파일** 메뉴를 차례로 클릭 **프로젝트**합니다.  
  
2.  클릭는 **Visual c + + 프로젝트** 폴더와 선택 **ATL 프로젝트**합니다.  
  
3.  형식 `Polygon` 프로젝트 이름으로 합니다.  
  
     소스 코드에 대 한 위치는 일반적으로 My Documents\Visual Studio 프로젝트와이 기본값으로 사용 하 고 새 폴더를 자동으로 생성 됩니다.  
  
4.  클릭 **확인** 및 ATL 프로젝트 마법사가 열립니다.  
  
5.  클릭 **응용 프로그램 설정** 사용할 수 있는 옵션을 표시 합니다.  
  
6.  컨트롤을 만드는 컨트롤 in-process 서버 여야 합니다 둡니다는 **응용 프로그램 종류** DLL로 합니다.  
  
7.  다른 옵션의 기본값을 그대로 사용 하 고 클릭 **마침**합니다.  
  
 ATL 프로젝트 마법사는 여러 개의 파일을 생성 하 여 프로젝트를 만듭니다. 솔루션 탐색기에서 다각형 개체를 확장 하 여 이러한 파일을 볼 수 있습니다. 파일은 다음과 같습니다.  
  
|파일|설명|  
|----------|-----------------|  
|Polygon.cpp|구현이 포함 되어 `DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`, 및 `DllUnregisterServer`합니다. 프로젝트의 ATL 개체의 목록인 개체 맵의 포함 됩니다. 이 옵션은 처음 비어 있습니다.|  
|Polygon.def|이 모듈 정의 파일 링커 DLL에서 필요로 하는 내보내기에 대 한 정보를 제공 합니다.|  
|마우스 오른쪽 단추로 Polygon.idl|인터페이스 정의 언어 파일을 개체에 특정 인터페이스를 설명 하는 합니다.|  
|Polygon.rgs|이 레지스트리 스크립트를 사용 하면 프로그램의 DLL을 등록 하는 것에 대 한 정보가 있습니다.|  
|Polygon.rc|초기 버전 정보 및 프로젝트 이름을 포함 하는 문자열을 포함 하는 리소스 파일입니다.|  
|Resource.h|리소스 파일에 대 한 헤더 파일입니다.|  
|Polygonps.def|이 모듈 정의 파일 링커 호출을 지 원하는 아파트 프록시 및 스텁 코드에서 필요로 하는 내보내기에 대 한 정보를 제공 합니다.|  
|stdafx.cpp|파일 내용이 `#include` ATL 구현 파일입니다.|  
|stdafx.h|파일 내용이 `#include` ATL 헤더 파일입니다.|  
  
1.  솔루션 탐색기에서 마우스 오른쪽 단추로 클릭는 `Polygon` 프로젝트.  
  
2.  바로 가기 메뉴를 클릭 **속성**합니다.  
  
3.  클릭 **링커**합니다. 변경 된 **UserRedirection 당** 옵션을 **예**합니다.  
  
4.  **확인**을 클릭합니다.  
  
 다음 단계에서는 프로젝트에는 컨트롤을 추가 합니다.  
  
 [2 단계로](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)

