---
title: "CAtlServiceModuleT::Handler Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule::Handler"
  - "CServiceModule.Handler"
  - "Handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Handler method"
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CAtlServiceModuleT::Handler Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CAtlServiceModuleT::Handler`서비스의 상태를 검색 하 고 \(중지 또는 일시 중지\) 등 다양 한 지침을 제공 하는 서비스 제어 관리자 \(SCM\)를 호출 하는 루틴이입니다.  SCM에는 작업 코드에 전달 `Handler` 어떻게 해야 서비스를 나타냅니다.  기본 ATL 생성 서비스는만 중지 명령을 처리합니다.  SCM 서비스 인식 중지 명령이 SCM을 전달 하는 경우 프로그램이 곧 중지 됩니다.  서비스를 호출 하 고 `PostThreadMessage` 종료 메시지 자체에 게시 합니다.  이 메시지 루프를 종료 하 고 해당 서비스도 종료 됩니다.  
  
 자세한 지침을 처리 하기 위해 변경 해야는 `m_status` 데이터 멤버는 초기화에 `CAtlServiceModuleT` 생성자.  이 데이터 멤버 SCM 서비스 제어판 응용 프로그램에서 서비스를 선택한 경우 사용 되는 단추를 알려 줍니다.  
  
## 참고 항목  
 [서비스](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../Topic/CAtlServiceModuleT::Handler.md)