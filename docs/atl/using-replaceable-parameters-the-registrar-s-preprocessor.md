---
title: 대체 가능 매개 변수 (ATL 등록자)를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AddReplacement
- ClearReplacements
dev_langs:
- C++
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91deabfd14d89c4a26384a14445fc51edbb3ac94
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362286"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>대체 가능 매개 변수를 사용 하 여 (등록자&#39;s 전처리기)
대체 가능 매개 변수 사용 등록자의 클라이언트 실행 시간 데이터를 지정할 수 있습니다. 이렇게 하려면 등록자에 관련 된 스크립트에 대 한 대체 가능 매개 변수 값을 입력 하는 대체 맵을 유지 관리 합니다. 등록자는 런타임 시 이러한 항목을 만듭니다.  
  
##  <a name="_atl_using_.25.module.25"></a> 모듈 % %를 사용 하 여  
 [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md) 자동으로 사용 하는 스크립트를 생성 `%MODULE%`합니다. ATL 서버 DLL 또는 EXE의 실제 위치에 대 한이 대체 가능 매개 변수를 사용합니다.  
  
## <a name="concatenating-run-time-data-with-script-data"></a>스크립트 데이터를 사용 하 여 런타임에 데이터를 연결합니다.  
 전처리기를 사용 하는 다른 스크립트 데이터를 사용 하 여 런타임에 데이터를 연결 하는 것입니다. 예를 들어 문자열을 사용 하 여 모듈에 전체 경로 포함 하는 항목이 필요 "`, 1`" 끝에 추가 됩니다. 첫째, 다음과 같은 확장을 정의 합니다.  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 그런 다음 호출 하기 전에 스크립트 처리에 나열 된 방법 중 하나 [스크립트 호출](../atl/invoking-scripts.md), 대체를 맵에 추가:  
  
 [!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]  
  
 등록자 확장의 구문 분석 중 스크립트의 `'%MODULE%, 1'` 를 `c:\mycode\mydll.dll, 1`합니다.  
  
> [!NOTE]
>  등록자 스크립트에서 4k는 최대 토큰 크기입니다. (토큰 구문에서 인식할 수 있는 모든 요소입니다.) 생성 되거나 전처리기에 의해 확장 된 토큰이 포함 됩니다.  
  
> [!NOTE]
>  런타임 시 대체 값을 대체할 호출을 제거 하려면 스크립트에 [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) 또는 [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) 매크로입니다. 대신, 사용자의 정보로 대체 `UpdateRegistry` 메서드를 호출 하는 [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) 또는 [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources), 의배열을전달 **_ATL_REGMAP_ENTRY** 구조입니다. 배열 **_ATL_REGMAP_ENTRY** 로 설정 된 항목이 하나 이상 있어야 합니다. {**NULL**,**NULL**},이 항목의 마지막 항목은 항상 및 합니다. 그렇지 않으면 액세스 위반 오류가 됩니다 때 생성 되 **UpdateRegistryFromResource** 호출 됩니다.  
  
> [!NOTE]
>  ATL 실행 시 만든 경로 이름 주위에 따옴표를 자동으로 추가 실행 파일을 출력 하는 프로젝트를 빌드할 때는 **% 모듈 %** 등록자 스크립트 매개 변수입니다. 경로 이름에서 인용 부호를 포함 하지 않으려면 사용 하 여 새 **묶지** 매개 변수 대신 합니다.  
>   
>  DLL을 출력 하는 프로젝트를 작성할 때 ATL 추가 하지 것입니다 인용 부호를 경로 이름으로 경우 **% 모듈 %** 또는 **묶지** 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)

