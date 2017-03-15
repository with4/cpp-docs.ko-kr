---
title: "프로젝트 만들기(ATL 자습서, 1부) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 프로젝트 만들기(ATL 자습서, 1부)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 자습서에서는 다각형을 표시 하는 ActiveX 개체를 만드는 특성된 ATL 프로젝트를 통해 단계별로 설명 합니다.  \[다각형\] 및 코드를 표시를 새로 고치려면 변의 개수를 변경 하 여 사용자가 옵션은 개체를 포함 합니다.  
  
> [!NOTE]
>  일반적으로 ATL 및 MFC의 Visual Studio Express 버전에서 지원 되지 않습니다.  
  
> [!NOTE]
>  이 자습서는 Polygon 샘플과 동일한 소스 코드를 만듭니다.  소스 코드를 수동으로 입력 하지 않도록 하려는 경우에 여기에서 다운로드할 수 있습니다는  [다각형 샘플 요약](../top/visual-cpp-samples.md).  자습서를 통해 작업을 사용 하 여 사용자의 고유한 프로젝트에서 오류를 검사 하 여 다음 다각형 소스 코드를 참조할 수 있습니다.  
  
### ATL 프로젝트 마법사를 사용 하 여 초기 ATL 프로젝트를 만들려면  
  
1.  Visual Studio 개발 환경에서를 클릭 합니다.  **New** 에  **파일** 메뉴를 클릭 하 고  **프로젝트**.  
  
2.  클릭 하 여  **Visual C\+\+ 프로젝트** 폴더 및 선택  **ATL 프로젝트**.  
  
3.  형식  `다각형` 프로젝트 이름입니다.  
  
     일반적으로 소스 코드의 위치로 My Documents\\Visual Studio 프로젝트 기본값으로 설정 됩니다 및 새 폴더가 자동으로 만들어집니다.  
  
4.  클릭  **확인** 하 고 ATL 프로젝트 마법사를 엽니다.  
  
5.  클릭  **응용 프로그램 설정** 사용할 수 있는 옵션을 볼 수 있습니다.  
  
6.  컨트롤을 만들고 컨트롤에는 in\-process 서버 여야 합니다, 그대로  **응용 프로그램 종류** dll입니다.  
  
7.  다른 옵션을 기본값 그대로 두고을 클릭  **마침**.  
  
 ATL 프로젝트 마법사는 프로젝트를 여러 개의 파일을 생성 하 여 만듭니다.  솔루션 탐색기에서 Polygon 개체를 확장 하 여 이러한 파일을 볼 수 있습니다.  파일 아래에 나열 됩니다.  
  
|파일|설명|  
|--------|--------|  
|Polygon.cpp|Contains the implementation of `DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`, and `DllUnregisterServer`.  또한 프로젝트에 ATL 개체 목록입니다 하는 오브젝트 맵이 들어 있습니다.  이 처음에 비어 있습니다.|  
|Polygon.def|이 모듈 정의 파일에서는 DLL에서 필요한 내보내기에 대 한 정보를 링커에 제공 합니다.|  
|Polygon.idl|개체에 특정 인터페이스에 설명의 인터페이스 정의 언어 파일.|  
|Polygon.rgs|이 레지스트리 스크립트 프로그램의 DLL을 등록 하는 것에 대 한 정보가 포함 되어 있습니다.|  
|Polygon.rc|처음에 버전 정보와 프로젝트 이름이 들어 있는 문자열을 포함 하는 리소스 파일입니다.|  
|Resource.h|리소스 파일의 헤더 파일|  
|Polygonps.def|이 모듈 정의 파일에서는 아파트 경계를 넘어 호출을 지 원하는 프록시와 스텁 코드에 필요한 내보내기에 대 한 정보를 링커에 제공 합니다.|  
|stdafx.cpp|파일 `#include` ATL 구현 파일입니다.|  
|stdafx.h|파일 `#include` ATL 헤더 파일입니다.|  
  
1.  솔루션 탐색기에서 마우스 오른쪽의 `Polygon` 프로젝트입니다.  
  
2.  바로 가기 메뉴에서 클릭  **속성**.  
  
3.  클릭  **링커**.  변경 된  **사용자 단위리디렉션** 옵션  **예**.  
  
4.  **확인**을 클릭합니다.  
  
 다음 단계에서는 프로젝트에 컨트롤을 추가 합니다.  
  
 [2 단계](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## 참고 항목  
 [자습서](../atl/active-template-library-atl-tutorial.md)