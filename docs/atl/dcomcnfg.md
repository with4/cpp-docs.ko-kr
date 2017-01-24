---
title: "DCOMCNFG | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DCOMCNFG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DCOM, configuring in ATL"
  - "DCOMCNFG utility"
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DCOMCNFG
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**DCOMCNFG** 다양 한 DCOM 관련 설정을 구성할 수 있는 Windows NT 4.0 유틸리티입니다.  **DCOMCNFG** 창 세 페이지에 있습니다: 기본 보안, 기본 속성 및 응용 프로그램.  Windows 2000에서 기본 프로토콜, 네 번째 페이지가 있습니다.  
  
## 기본 보안 페이지  
 기본 보안 페이지에서 시스템 개체에 대 한 기본 사용 권한을 지정할 수 있습니다.  기본 보안 페이지에 세 가지 섹션이 있습니다: 액세스, 시작 및 구성 합니다.  해당 섹션의 기본값을 변경 하려면 클릭  **기본값 편집** 단추.  이러한 기본 보안 설정 아래에 저장 된 `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.  
  
## 기본 프로토콜 페이지  
 이 페이지가이 컴퓨터의 DCOM에 사용할 수 있는 네트워크 프로토콜 집합을 나열합니다.  사용 되는 우선 순위 순서를 반영 합니다. 첫 번째 목록에서 우선 순위가 가장 높은 있습니다.  프로토콜 추가 하거나이 페이지에서 삭제할 수 있습니다.  
  
## 기본 속성 페이지  
 기본 속성 페이지에서 선택 해야의  **이 컴퓨터에서 DCOM 사용** 클라이언트에서 다른 컴퓨터 액세스 COM 개체를 실행 하려는 경우 확인란.  이 옵션 설정을 선택 하는 `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` 값 `Y`.  
  
## 응용 프로그램 페이지  
 응용 프로그램 페이지에는 특정 개체에 대 한 설정을 변경 합니다.  단순히 응용 프로그램을 목록에서 선택 하 고 클릭 된  **속성** 단추.  속성 창 5 개의 페이지가 있습니다.  
  
-   일반 페이지를 사용 하는 응용 프로그램을 확인 합니다.  
  
-   위치 페이지의 클라이언트에서 호출할 때 응용 프로그램을 실행할 위치를 지정할 수 있습니다 `CoCreateInstance` 에 관련 된 CLSID입니다.  선택 하면는  **다음 컴퓨터에서 응용 프로그램을 실행** 확인란을 선택 하 고 컴퓨터 이름을 입력 후에 `RemoteServerName` Appid에 대 한 해당 응용 프로그램에서 값을 추가 합니다.  지우기는  **이 컴퓨터에서 응용 프로그램 실행** 확인란 이름 바꾸기는 `LocalService` 값 `_LocalService` 하 여 사용할 수 없습니다.  
  
-   기본 보안 페이지를 찾을 수 있는 보안 페이지 유사는  **DCOMCNFG** 창에서 이러한 설정을 현재 응용 프로그램에만 적용 된다는.  다시 아래 AppID 해당 개체에 대 한 설정이 저장 됩니다.  
  
-   사용자 응용 프로그램을 실행 하는 데 사용 됩니다 식별 페이지를 식별 합니다.  
  
-   끝점 페이지 선택한 DCOM 서버의 클라이언트가 사용할 수 있는 끝점 및 프로토콜 집합을 나열합니다.  
  
## 참고 항목  
 [서비스](../atl/atl-services.md)