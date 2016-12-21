---
title: "Visual C++에서 ActiveX 컨트롤을 사용하여 데이터 바인딩 | Microsoft Docs"
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
  - "ActiveX 컨트롤[C++], 데이터 바인딩"
  - "바인딩 컨트롤[C++], ActiveX"
  - "컨트롤[C++], 데이터 바인딩"
  - "데이터 바인딩[C++], ActiveX 컨트롤"
  - "데이터 바인딩 컨트롤[C++], ActiveX"
ms.assetid: afe11d2b-eefe-43ce-958d-82d3d4dee158
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++에서 ActiveX 컨트롤을 사용하여 데이터 바인딩
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 바인딩은 두 종류의 ActiveX 컨트롤, 즉 데이터 컨트롤과 데이터 바인딩된 컨트롤을 통해 구현됩니다.  
  
 **데이터 컨트롤**  
 데이터 컨트롤은 데이터베이스 쿼리와 검색된 행 집합을 캡슐화하는 작업을 담당합니다.  Microsoft 데이터 컨트롤은 데이터를 통해 반복하는 일련의 단추로 구성된 사용자 인터페이스를 제공합니다.  Visual C\+\+는 데이터 컨트롤에 [ADO 및 RDO](../../data/ado-rdo/data-access-ado-and-rdo.md)라는 두 가지 데이터 액세스 기술을 제공합니다.  
  
> [!IMPORTANT]
>  ADO 및 RDO 데이터 컨트롤은 Visual Studio의 이전 버전에서 릴리스된 레거시 기술이며 현재 버전에서는 사용하지 못 할 수 있습니다.  이 섹션의 정보를 사용하려면, 적절한 컨트롤을 취득하도록 이전 릴리스를 가져와야 할 수도 있습니다.  
  
 **데이터 바인딩된 컨트롤**  
 데이터 바인딩된 컨트롤은 데이터를 제공하는 작업을 담당합니다.  데이터 바인딩된 컨트롤은 데이터 컨트롤에 연결하여 데이터를 받고 다양한 사용자 인터페이스를 통해 데이터를 제공합니다.  Visual C\+\+ 응용 프로그램도 데이터 바인딩된 컨트롤에서 설정한 데이터 값에 변수를 바인딩할 수 있습니다. [CWnd::BindProperty](../Topic/CWnd::BindProperty.md)을 참조하십시오.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [MFC ActiveX 컨트롤: ActiveX 컨트롤에서 데이터 바인딩 사용하기](../../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)  
  
-   [데이터 액세스: ADO 및 RDO](../../data/ado-rdo/data-access-ado-and-rdo.md)  
  
-   [ADO 데이터 바인딩](../../data/ado-rdo/ado-databinding.md)  
  
-   [RDO 데이터 바인딩](../../data/ado-rdo/rdo-databinding.md)  
  
-   [래퍼 클래스](../../data/ado-rdo/wrapper-classes.md)  
  
-   [ActiveX 컨트롤에 이벤트 처리기 설정](../../data/ado-rdo/setting-event-handlers-on-activex-controls.md)  
  
-   [오류 트래핑](../../data/ado-rdo/error-trapping.md)  
  
-   [데이터 바인딩의 한계](../../data/ado-rdo/limitations-of-databinding.md)  
  
## 참고 항목  
 [데이터 바인딩된 컨트롤\(ADO 및 RDO\)](../../data/ado-rdo/data-bound-controls-ado-and-rdo.md)