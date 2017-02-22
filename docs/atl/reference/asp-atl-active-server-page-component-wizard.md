---
title: "ASP, ATL Active Server Page 구성 요소 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.asp.asp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL Active Server Page 구성 요소 마법사, ASP"
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ASP, ATL Active Server Page 구성 요소 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL Active Server Page 구성 요소 마법사의 이 페이지에서는 ASP 구성 요소 관련 정보와 상태를 처리하는 옵션을 설정합니다.  
  
 **선택적 메서드**  
 선택적 ASP 메서드인 **OnStartPage**와 **OnEndPage**를 개체에 추가합니다.  Active Server Pages 내장 개체를 설정하려면 이 옵션을 선택해야 합니다.  기본적으로 이 옵션은 선택되어 있습니다.  
  
-   **OnStartPage\/OnEndPage** [OnStartPage](https://msdn.microsoft.com/en-us/library/ms691624.aspx)는 스크립트에서 처음으로 개체에 액세스를 시도할 때 호출됩니다.  **OnEndPage**는 개체에서 스크립트 처리를 마칠 때 호출됩니다.  
  
 **내장 개체**  
 ASP 내장 개체를 설정하려면 **OnStartPage\/OnEndPage** 옵션을 선택해야 합니다.  
  
|옵션|설명|  
|--------|--------|  
|**요청**|Active Server Pages 내장 **요청** 개체에 대한 액세스를 제공합니다.  요청 개체는 HTTP 요청을 전달하는 데 사용됩니다.|  
|**응답**|Active Server Pages 내장 **응답** 개체에 대한 액세스를 제공합니다.  요청에 대한 응답으로 응답 개체는 정보를 브라우저로 보내 사용자에게 표시합니다.|  
|**세션**|Active Server Pages 내장 **세션** 개체에 대한 액세스를 제공합니다.  **세션** 개체는 상태 정보를 저장하고 검색할 뿐 아니라 현재 사용자 세션에 대한 정보를 유지 관리합니다.|  
|**Application**|Active Server Pages 내장 **응용 프로그램** 개체에 대한 액세스를 제공합니다.  **응용 프로그램** 개체는 여러 ASP 개체 간에 공유되는 상태를 관리합니다.|  
|**서버**|Active Server Pages 내장 **서버** 개체에 대한 액세스를 제공합니다.  **서버** 개체를 사용하면 다른 ASP 개체를 만들 수 있습니다.|  
  
## 참고 항목  
 [ATL Active Server Page 구성 요소 마법사](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)