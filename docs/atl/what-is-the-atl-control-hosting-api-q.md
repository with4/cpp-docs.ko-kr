---
title: 란 ATL 컨트롤 호스팅 API? | Microsoft 문서
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
ms.openlocfilehash: 30b104e21259006da41c236c168431d85b43e0d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363248"
---
# <a name="what-is-the-atl-control-hosting-api"></a>란 ATL 컨트롤 호스팅 API?
ATL 컨트롤 호스팅의 API를 사용 하면 모든 창이 ActiveX 컨트롤 컨테이너 역할을 하는 함수 집합입니다. 이러한 함수 구현 해야 합니다 또는 동적으로 소스 코드로 사용할 수 있기 때문에 프로젝트에 연결 하 고이 노출 ATL90.dll 하 여 만듭니다. 컨트롤 호스팅 함수는 아래 표에 나열 됩니다.  
  
|함수|설명|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|호스트 개체를 만듭니다, 그리고 제공된 된 창에 연결한 다음 기존 컨트롤에 첨부 합니다.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|호스트 개체를 만듭니다를 다음 제공된 된 창에 연결 된 컨트롤을 로드 합니다.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|사용 허가 받은 ActiveX 컨트롤을 만들고 초기화를 유사 하며 지정한 창에 호스팅합니다 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)합니다.|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|호스트 개체를 만듭니다, 제공된 된 창에 연결한 다음 컨트롤 로드 (또한를 통해 이벤트 싱크를 설정 해야) 합니다.|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|사용 허가 받은 ActiveX 컨트롤을 만들고 초기화를 유사 하며 지정한 창에 호스팅합니다 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)합니다.|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|대화 상자 리소스에서 모덜리스 대화 상자를 만들고 창 핸들을 반환 합니다.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|대화 상자 리소스에서 모달 대화 상자를 만듭니다.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|반환 된 **IUnknown** 창에서에서 호스트 컨트롤의 인터페이스 포인터입니다.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|반환 된 **IUnknown** 창에 연결 된 호스트 개체의 인터페이스 포인터입니다.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|컨트롤 호스팅 코드를 초기화합니다.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|컨트롤 호스팅 코드 초기화를 취소 합니다.|  
  
 `HWND` 처음 세 개의 함수에서 매개 변수는 거의 모든 형식의 기존 창 이어야 합니다. 이러한 세 가지 함수를 명시적으로 호출 하는 경우 (일반적으로 않아도)을 이미 역할을 호스트 하는 창에 대 한 핸들을 전달 하지 마세요 (이렇게 하면 기존 호스트 개체 않습니다 사용 가능).  
  
 처음 7 함수 호출 [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) 암시적으로 합니다.  
  
> [!NOTE]
>  컨트롤 호스팅 API ActiveX 컨트롤 포함에 대 한 ATL의 지원의 기초를 형성합니다. 그러나는 일반적으로 활용 하기 위해 또는 ATL의 래퍼 클래스를 최대한 활용 하는 경우 이러한 함수를 직접 호출할 필요가 거의 합니다. 자세한 내용은 참조 [는 ATL 클래스 용이 하 게 ActiveX 컨트롤 포함](which-atl-classes-facilitate-activex-control-containment-q.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 포함 FAQ](which-atl-classes-facilitate-activex-control-containment-q.md)
