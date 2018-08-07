---
title: 새로운 ATL 컨트롤 호스팅 API? | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- APIs [C++], hosting
- control-hosting API
- controls [ATL], hosting APIs
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc85c7ca47d5d1226ffc3089e01c0755ef6c6ac
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850556"
---
# <a name="what-is-the-atl-control-hosting-api"></a>새로운 ATL 컨트롤 호스팅 API?
ATL의 컨트롤 호스팅 API는 ActiveX 컨트롤 컨테이너 역할을 허용 하는 함수 집합입니다. 이러한 함수 정적으로 또는 동적으로 소스 코드로 제공 되므로 프로젝트에 연결 되며 ATL90.dll에 의해 노출 합니다. 컨트롤 호스팅 함수는 아래 표에 나열 됩니다.  
  
|기능|설명|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|호스트 개체를 만듭니다, 그리고 제공된 된 창에 연결한 다음 기존 컨트롤을 연결 합니다.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|호스트 개체를 만듭니다, 그리고 제공된 된 창에 연결한 다음 컨트롤을 로드 합니다.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|사용이 허가 된 ActiveX 컨트롤을 만들고, 초기화 및 비슷하게 지정 된 창에서 호스트 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)합니다.|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|호스트 개체를 만들고, 제공된 된 창에 연결한 다음 컨트롤을 로드 (또한를 통해 이벤트 싱크 설정).|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|사용이 허가 된 ActiveX 컨트롤을 만들고, 초기화 및 비슷하게 지정 된 창에서 호스트 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)합니다.|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|대화 상자 리소스에서 모덜리스 대화 상자를 만들고 창 핸들을 반환 합니다.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|대화 상자 리소스에서 모달 대화 상자를 만듭니다.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|반환 된 `IUnknown` 창에서 호스팅되는 컨트롤의 인터페이스 포인터입니다.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|반환 된 `IUnknown` 창에 호스트 개체의 인터페이스 포인터에 연결 합니다.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|컨트롤 호스팅 코드를 초기화합니다.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|컨트롤 호스팅 코드를 초기화 하지 않습니다.|  
  
 `HWND` 처음 세 함수에 매개 변수 (거의) 모든 종류의 기존 창을 이어야 합니다. 이러한 세 가지 함수를 명시적으로 호출 하는 경우 (일반적으로 않아도)을 이미 역할을 호스트 하는 창에 대 한 핸들을 전달 하지 않습니다 (이렇게 하면 기존 호스트 개체 않습니다 해제) 합니다.  
  
 처음 7 개의 함수 호출 [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) 암시적으로 합니다.  
  
> [!NOTE]
>  컨트롤 호스팅 API는 ActiveX 컨트롤 포함에 대 한 ATL의 지원의 기초를 구성 합니다. 그러나 방법이 일반적으로 활용 하거나 ATL의 래퍼 클래스를 최대한 활용 하는 경우 이러한 함수를 직접 호출할 필요는 없습니다. 자세한 내용은 [는 ATL 클래스 용이 하 게 ActiveX 컨트롤 포함](which-atl-classes-facilitate-activex-control-containment-q.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 포함 FAQ](which-atl-classes-facilitate-activex-control-containment-q.md)
