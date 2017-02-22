---
title: "Composite Control Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "복합 컨트롤, 전역 함수"
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Composite Control Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 함수는 대화 상자 만들기, 만들기, 호스팅 및 ActiveX 컨트롤 라이센스 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|모달 대화 상자에서 사용자가 제공 하는 대화 상자 템플릿을 만듭니다.  대화 상자가 열리면 ActiveX 컨트롤을 포함할 수 있습니다.|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|모덜리스 대화 상자에서 사용자가 제공 하는 대화 상자 템플릿을 만듭니다.  대화 상자가 열리면 ActiveX 컨트롤을 포함할 수 있습니다.|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|ActiveX 컨트롤을 만들고, 초기화를 호스팅하는 지정 된 창에.|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|ActiveX 컨트롤은 초기화, 지정 된 창에서 호스팅하 만들고 인터페이스 포인터 \(또는 포인터\)을 컨트롤에서 검색 합니다.|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|ActiveX 사용이 허가 된 컨트롤 초기화를 만들고 호스팅하는 지정한 창에.|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|ActiveX 사용이 허가 된 컨트롤을 만들고 초기화, 지정 된 창에서 호스팅하 및 인터페이스 포인터 \(또는 포인터\)을 컨트롤에서 검색 합니다.|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|지정한 창에 이전에 만든된 컨트롤을 연결합니다.|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|지정 된 창 \(있는 경우\)에 대 한 컨테이너를 직접 인터페이스 포인터를 가져오는 데 핸들을 지정 합니다.|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|지정한 창 안에 \(있는 경우\)에 포함 된 컨트롤에 대 한 직접 인터페이스 포인터를 가져오는 데 핸들을 지정 합니다.|  
|[AtlSetChildSite](../Topic/AtlSetChildSite.md)|초기화는  **IUnknown** 하위 사이트입니다.|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|AxWin 개체에 대 한 호스팅 코드를 초기화합니다.|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|AxWin 개체에 대 한 호스팅 코드를 초기화 하지 않습니다.|  
|[AtlGetObjectSourceInterface](../Topic/AtlGetObjectSourceInterface.md)|개체의 기본 소스 인터페이스에 대 한 정보를 반환합니다.|  
  
## 참고 항목  
 [함수](../../atl/reference/atl-functions.md)   
 [Composite Control Macros](../../atl/reference/composite-control-macros.md)