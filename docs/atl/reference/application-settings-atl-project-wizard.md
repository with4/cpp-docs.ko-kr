---
title: "응용 프로그램 설정, ATL 프로젝트 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.atl.com.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트 마법사, 응용 프로그램 설정"
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
caps.latest.revision: 17
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 응용 프로그램 설정, ATL 프로젝트 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 프로젝트 마법사의 **응용 프로그램 설정** 페이지를 사용하여 기본 기능을 디자인하고 새 ATL 프로젝트에 추가합니다.  
  
## 서버 유형  
 다음 세 가지 서버 유형 중 하나를 선택합니다.  
  
 **동적 연결 라이브러리\(DLL\)**  
 in\-process 서버를 만들려면 이 옵션을 선택합니다.  
  
 **실행 파일\(EXE\)**  
 로컬 out\-of\-process 서버를 만들려면 이 옵션을 선택합니다.  이 옵션은 MFC 또는 COM\+ 1.0에 대한 지원이나  프록시\/스텁 코드 병합을 허용하지 않습니다.  
  
 **서비스\(EXE\)**  
 Windows가 시작될 때 백그라운드로 실행되는 Windows 응용 프로그램을 만들려면 이 옵션을 선택합니다.  이 옵션은 MFC 또는 COM\+ 1.0에 대한 지원이나 프록시\/스텁 코드 병합을 허용하지 않습니다.  
  
## 추가 옵션  
  
> [!NOTE]
>  모든 추가 옵션은 DLL 프로젝트에만 사용할 수 있습니다.  
  
 **프록시\/스텁 코드 병합 허용**  
 인터페이스를 마샬링해야 할 경우 편의상 **프록시\/스텁 코드 병합 허용** 확인란을 선택합니다.  이 옵션을 선택하면 MIDL 생성 프록시와 스텁 코드가 서버와 같은 실행 파일에 배치됩니다.  
  
 **지원 MFC**  
 개체에 MFC 지원이 포함되도록 하려면 이 옵션을 선택합니다.  이 옵션을 선택하면 MFC 라이브러리에 포함된 클래스와 함수에 액세스할 수 있도록 프로젝트가 MFC 라이브러리에 연결됩니다.  
  
 **지원 COM\+ 1.0**  
 COM\+ 1.0 구성 요소를 지원하도록 프로젝트 빌드 설정을 수정하려면 이 옵션을 선택합니다.  이 옵션을 선택하면 기본 라이브러리 목록 외에 COM\+ 1.0 구성 요소 관련 라이브러리인 comsvcs.lib가 추가됩니다.  
  
 또한 mtxex.dll은 응용 프로그램이 시작될 때 호스트 시스템에 지연 로드됩니다.  
  
-   **구성 요소 등록자 지원** ATL 프로젝트에 COM \+ 1.0 구성 요소 지원이 포함 된 경우이 옵션을 설정할 수 있습니다.  구성 요소 등록자를 사용하면 COM\+ 1.0 개체는 구성 요소 목록을 얻거나, 개별적으로 또는 한꺼번에 구성 요소를 등록하거나 등록 취소할 수 있습니다.  
  
## 참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)