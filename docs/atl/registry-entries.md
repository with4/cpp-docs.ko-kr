---
title: "Registry Entries | Microsoft Docs"
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
  - "레지스트리, application IDs"
  - "레지스트리, ATL services entries"
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Registry Entries
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM 응용 프로그램에 중앙된 위치에 레지스트리 DCOM 개체에 대 한 구성 옵션을 그룹 Id \(Appid\)의 개념을 도입 했습니다.  값에서 명명 된 값에서 개체의 CLSID에서 AppID 나타내는 Appid를 지정 합니다.  
  
 기본적으로 ATL 생성 서비스는 해당 CLSID 해당 Appid에 대 한 GUID로 사용 합니다.  아래 `HKEY_CLASSES_ROOT\AppID`, DCOM 관련 항목을 지정할 수 있습니다.  처음에 두 가지 항목이 있습니다.  
  
-   `LocalService`서비스의 이름에 동일한 값을 가진.  이 값이 존재 하는 경우 대신 사용 되는 `LocalServer32` 의 CLSID 아래에 키.  
  
-   `ServiceParameters`값이 크거나 `–Service`.  이 값이 시작 될 때 서비스에 전달할 매개 변수를 지정 합니다.  참고 이러한 매개 변수를 서비스에 전달 된 `ServiceMain` 작동 하지 `WinMain`.  
  
 또한 모든 DCOM 서비스에서 다른 키를 만들 필요가 `HKEY_CLASSES_ROOT\AppID`.  이 키 exe 파일 이름으로이 고 상호 참조로 역할을 하는 AppID 항목을 가리키는 AppID 값 포함 되어 있습니다.  
  
## 참고 항목  
 [서비스](../atl/atl-services.md)