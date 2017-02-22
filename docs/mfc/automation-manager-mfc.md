---
title: "자동화 관리자(MFC) | Microsoft Docs"
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
  - "AUTMGR32.exe"
  - "자동화 클라이언트, 자동화 관리자"
  - "자동화 관리자"
  - "자동화 서버, 자동화 관리자"
  - "자동화, 자동화 관리자"
  - "원격 자동화, 자동화 관리자"
ms.assetid: 6bf3429e-1946-41c5-86d0-ad7f5b8585b8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 자동화 관리자(MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

AUTMGR32.EXE should be copied to the Windows system directory of each machine that is intending to provide Remote Automation objects.  For Windows 95 and Windows 98, this directory is typically C:\\WINDOWS\\SYSTEM.  For Windows NT and Windows 2000, it is typically C:\\WINNT\\SYSTEM32.  
  
 If you want to enable callbacks from the server to the client, this executable file should also be copied to the system directory of each client machine.  
  
 When the Automation Manager is running, it displays a small window on the server machine that contains brief status information.  If you want to hide it, refer to article Q138067 in the Microsoft Knowledge Base.  
  
## 참고 항목  
 [원격 자동화 연결 관리자](../mfc/remote-automation-connection-manager.md)   
 [원격 자동화 사용자 구성 요소](../mfc/remote-automation-user-components.md)   
 [원격 자동화 설치](../mfc/remote-automation-installation.md)