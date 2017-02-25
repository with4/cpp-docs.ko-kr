---
title: "MAPI | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "전자 메일, 사용"
  - "응용 프로그램에서 메일 사용"
  - "응용 프로그램에서 MAPI 사용"
  - "메일, 응용 프로그램 사용으로 설정"
  - "MFC의 MAPI 지원"
  - "MAPI, MFC"
  - "메시징, 클라이언트 응용 프로그램"
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MAPI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 클라이언트 메시지 응용프로그램 개발자들을 위한 마이크로 소프트 메시징 응용프로그래밍 인터페이스\(MAPI\)에 대해서 설명합니다.  MFC 지원은 **CDocument** 클래스에서 MAPI의 하위 집합에 대해 지원하지만 전체 API를 캡슐화 하지 않습니다.  자세한 내용은 [MAPI Support in MFC](../mfc/mapi-support-in-mfc.md)을 참조하십시오.  
  
 MAPI는 메일 사용 가능 및 메일 인식 응용 프로그램 만들기, 조작, 전송 및 메일 메시지를 저장 하는 기능입니다.  응용 프로그램 개발자에게 목적 및 메일 메시지의 내용을 정의 하는 도구를 제공하고 저장된 메일 메시지 관리에서 유연성을 제공 합니다.  MAPI 는 또한 응용프로그램 개발자들이 근본적인 메시징 시스템과 독립적으로 사용가능한 메일과 메일 인식 응용프로그램을 생성할 때 사용할 수 있는 공통 인터페이스를 제공합니다.  
  
 메시징 클라이언트는 마이크로소프트 윈도우즈 메시징 시스템\(WMS\)와의 상호 작용을 위한 휴먼 인터페이스를 제공합니다.  이 상호작용은 일반적으로 미시지 저장소와 주소록과 같은 MAPI 호환 공급자로부터 서비스를 요청하는 것을 포함합니다.  
  
 MAPI에 대 한 자세한 내용은 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]의 Win32 메시징\(MAPI\)의 가이드 아래의 문서를 참조하십시오.  
  
## 단원 내용  
 [MFC의 MAPI 지원](../mfc/mapi-support-in-mfc.md)  
  
## 참고 항목  
 [CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)   
 [CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)   
 [COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)