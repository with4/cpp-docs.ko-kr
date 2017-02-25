---
title: "사용자 지정의 보안 의미 | Microsoft Docs"
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
  - "MFC 기능 팩, 보안"
  - "보안, MFC 기능 팩"
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 사용자 지정의 보안 의미
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This topic discusses a potential security weakness in MFC.  
  
## Potential Security Weakness  
 MFC allows the user customize the look of an application user interface, for example, the appearance of buttons and icons.  MFC also supports user\-defined tools, which let the user execute shell commands.  A security vulnerability arises because the customized settings of the application are saved in the user profile in the registry.  Anyone who can access the registry can edit those settings and change the application appearance or behavior.  For example, an administrator on the computer could impersonate a user by causing the user's application to execute arbitrary programs \(even from a network share\).  
  
## 해결 방법  
 We recommend any of these three ways to close the vulnerabilities in the registry:  
  
-   Encrypt the data that is stored there  
  
-   Store the data in a secure file instead of in the registry.  
  
     To accomplish either of these first two ways, derive a class from [CSettingsStore Class](../mfc/reference/csettingsstore-class.md) and override its methods to implement encryption or storage outside the registry.  
  
-   You can also disable customizations in your application.  
  
## 참고 항목  
 [MFC에 대한 사용자 지정](../mfc/customization-for-mfc.md)