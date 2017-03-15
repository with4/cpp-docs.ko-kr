---
title: "What Is the ATL Control-Hosting API? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "API[C++], 호스팅"
  - "control-hosting API"
  - "컨트롤[ATL], API 호스팅"
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
caps.latest.revision: 15
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# What Is the ATL Control-Hosting API?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL의 컨트롤 호스팅 API ActiveX 컨트롤 컨테이너로 작동 하는 창 수 함수 집합입니다.  이러한 정적 수 또는 동적으로 소스 코드로 사용할 수 있으므로 프로젝트에 연결 된 함수와 ATL90.dll 여 노출.  컨트롤 호스팅 함수는 아래 표에 나와 있습니다.  
  
|Function|설명|  
|--------------|--------|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|호스트 개체를 만들어 제공 된 창에 연결한 다음 기존 컨트롤에 첨부 합니다.|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|호스트 개체를 만들어 제공 된 창에 연결한 다음 컨트롤을 로드 합니다.|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|ActiveX 사용이 허가 된 컨트롤 초기화를 만들고 지정한 창에서 유사한 호스트  [AtlAxCreateControl](../Topic/AtlAxCreateControl.md).|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|호스트 개체를 만들어 제공 된 창에 연결한 다음 컨트롤을 로드 \(이벤트 싱크 설정할 수도 있습니다\).|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|ActiveX 사용이 허가 된 컨트롤 초기화를 만들고 지정한 창에서 유사한 호스트  [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md).|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|창 핸들을 반환 하 고 대화 상자 리소스에서 모덜리스 대화 상자를 만듭니다.|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|모달 대화 상자에서 대화 상자 리소스를 만듭니다.|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|반환 된  **IUnknown** 창에 호스팅된 컨트롤에 대 한 인터페이스 포인터입니다.|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|반환 된  **IUnknown** 호스트 개체의 인터페이스 포인터를 창에 연결 합니다.|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|컨트롤 호스팅 코드를 초기화합니다.|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|컨트롤 호스팅 코드를 초기화 하지 않습니다.|  
  
 `HWND` 처음 세 개의 함수에 매개 변수는 거의 모든 형식의 기존 창 이어야 합니다.  이러한 세 가지 함수를 명시적으로 호출 하는 경우 \(일반적으로 사용자 필요가 없습니다\), 이미 호스트 역할을 하는 창 핸들을 전달 하지 않습니다 \(이렇게 하면 기존 호스트 개체가 해제 되지 않습니다\).  
  
 처음 7 개의 함수 호출  [AtlAxWinInit](../Topic/AtlAxWinInit.md) 암시적으로.  
  
> [!NOTE]
>  컨트롤 호스팅 API 지원 ATL의 컨트롤 포함 기능 ActiveX의 기초를 형성합니다.  그러나 이용 또는 전체 ATL의 래퍼 클래스를 사용 하는 경우 이러한 함수를 직접 호출할 필요가 있습니다 일반적으로.  자세한 내용은  [는 ATL 클래스를 쉽게 ActiveX 컨트롤을 포함할?](../atl/which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## 참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)