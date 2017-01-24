---
title: "원격 자동화 사용자 구성 요소 | Microsoft Docs"
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
  - "DLL[C++], 자동화"
  - "원격 자동화[C++], 사용자 구성 요소"
ms.assetid: 601591cc-a442-440a-988e-baf3284b0d46
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 원격 자동화 사용자 구성 요소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You will need to ensure that each client machine contains your client program and any support DLLs it requires.  You will also need to ensure that the server application and any support DLLs it requires are present on the server machine.  Finally, you will need to ensure that your server program is registered on each client machine before RAC Manager can be run to configure the connection.  If the program is self\-registering \(as most will be\), you need only execute the server program on the client machine to register it.  Failing that, you may have to execute a registration file that you provide, or manually edit the registry.  
  
## 참고 항목  
 [자동화 관리자\(MFC\)](../mfc/automation-manager-mfc.md)   
 [원격 자동화 연결 관리자](../mfc/remote-automation-connection-manager.md)   
 [원격 자동화 설치](../mfc/remote-automation-installation.md)