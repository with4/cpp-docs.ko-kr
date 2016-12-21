---
title: "ATL OLE DB 소비자 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL OLE DB 소비자"
  - "ATL 프로젝트, ATL OLE DB 소비자 추가"
  - "OLE DB, 프로젝트에 ATL OLE DB 소비자 추가"
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL OLE DB 소비자 추가
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 마법사를 사용하여 ATL OLE DB 소비자를 프로젝트에 추가합니다.  ATL OLE DB 소비자는 데이터 소스에 액세스하는 데 필요한 OLE DB 접근자 클래스와 데이터 바인딩으로 구성됩니다.  프로젝트는 ATL COM 응용 프로그램으로 만들거나 ATL OLE DB 소비자 마법사를 통해 자동으로 추가되는 ATL을 지원하는 MFC나 Win32 응용 프로그램으로 만들어야 합니다.  
  
 **참고**  OLE DB 소비자를 MFC 프로젝트에 추가할 수 있습니다.  이렇게 하면 ATL OLE DB 소비자 마법사는 필요한 COM 지원을 프로젝트에 추가합니다.  이 경우, MFC 프로젝트를 만들 때 MFC 프로젝트 응용 프로그램 마법사의 **고급 기능** 페이지에서 기본적으로 선택되어 있는 **ActiveX 컨트롤** 확인란을 선택했다고 가정합니다.  이 옵션을 선택하면 응용 프로그램에서 **CoInitialize** 및 **CoUninitialize**를 호출합니다  MFC 프로젝트를 만들 때 **ActiveX 컨트롤**을 선택하지 않은 경우에는 메인 코드에서 **CoInitialize** 및 **CoUninitialize**를 호출해야 합니다.  
  
### ATL OLE DB 소비자를 프로젝트에 추가하려면  
  
1.  클래스 뷰에서 프로젝트를 마우스 오른쪽 단추로 클릭합니다.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
2.  Visual C\+\+ 폴더에서 **ATL OLE DB 소비자** 아이콘을 두 번 클릭하거나 아이콘을 선택한 후 **열기**를 클릭합니다.  
  
     ATL OLE DB 소비자 마법사가 열립니다.  
  
3.  [ATL OLE DB 소비자 마법사](../../atl/reference/atl-ole-db-consumer-wizard.md)의 설명에 따라 설정을 정의합니다.  
  
4.  **마침**을 클릭하여 마법사를 닫습니다.  새로 만들어진 OLE DB 소비자 코드가 프로젝트에 삽입됩니다.  
  
## 참고 항목  
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)