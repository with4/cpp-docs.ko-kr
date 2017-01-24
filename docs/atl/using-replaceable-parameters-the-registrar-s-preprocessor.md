---
title: "Using Replaceable Parameters (The Registrar&#39;s Preprocessor) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddReplacement"
  - "ClearReplacements"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%MODULE%"
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using Replaceable Parameters (The Registrar&#39;s Preprocessor)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대체 가능 매개 변수는 등록자의 클라이언트가 런타임 데이터를 지정할 수 있습니다.  이 위해서는 등록자를 대체 가능한 매개 변수를 스크립트에 연결 된 값을 입력 하는 대체 맵을 유지 관리 합니다.  등록자는 런타임에 이러한 항목을 만듭니다.  
  
##  <a name="_atl_using_.25.module.25"></a> %MODULE% 사용 하 여  
 [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md) 사용 하는 스크립트를 자동으로 생성 `%MODULE%`.  ATL 서버 DLL 또는 EXE의 실제 위치에 대 한이 대체 가능한 매개 변수를 사용합니다.  
  
## 런타임 데이터와 스크립트 데이터 연결  
 전처리기를 사용 하는 다른 런타임 데이터와 스크립트 데이터를 연결 하는 것입니다.  항목의 전체 경로를 문자열을 사용 하 여 모듈을 포함에 필요한 예를 들어 "`, 1`"의 끝에 추가 합니다.  먼저, 다음과 같은 확장을 정의 합니다.  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 그런 다음 이전 호출 처리 방법에 나열 된 스크립트 중 하나  [스크립트 호출](../atl/invoking-scripts.md), 대체 지도에 추가:  
  
 [!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/CPP/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]  
  
 등록자는 스크립트의 구문 분석 중, 확장 `'%MODULE%, 1'` 에 `c:\mycode\mydll.dll, 1`.  
  
> [!NOTE]
>  등록자 스크립트에서 최대 토큰 크기는 4k입니다.  \(토큰 구문에서 인식이 가능한 요소입니다.\) 여기에 토큰 만들어졌거나 전처리기에서 확장.  
  
> [!NOTE]
>  런타임 시 대체 값을 대체 하기 위해 스크립트를 호출 제거는  [DECLARE\_REGISTRY\_RESOURCE](../Topic/DECLARE_REGISTRY_RESOURCE.md) 또는  [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md) 매크로.  대신에 자신의 대체 `UpdateRegistry` 메서드를 호출 하는  [CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md) 또는  [CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md)에 배열을 전달 하 고  **\_ATL\_REGMAP\_ENTRY** 구조.  배열에  **\_ATL\_REGMAP\_ENTRY** 설정 하려면 적어도 하나의 항목이 있어야 합니다 {**NULL**,**NULL**}를 하 고이 항목이 항상 마지막 항목 이어야 합니다.  그렇지 않으면 수 액세스 위반 오류가 생성 시  **UpdateRegistryFromResource** 라고 합니다.  
  
> [!NOTE]
>  실행 파일을 출력 하는 프로젝트를 빌드할 때 ATL 자동으로 런타임에 만들어진 경로 이름 앞뒤에 따옴표를 추가 된  **%MODULE%** 등록자 스크립트 매개 변수.  경로 이름을 따옴표를 사용 하지 않으려면 새 사용  **%module\_raw%** 매개 변수 대신.  
>   
>  DLL을 출력 하는 프로젝트를 빌드할 때 ATL 따옴표로 경로 이름에 경우 추가 되지 않습니다  **%MODULE%** 또는  **%module\_raw%** 사용 됩니다.  
  
## 참고 항목  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)