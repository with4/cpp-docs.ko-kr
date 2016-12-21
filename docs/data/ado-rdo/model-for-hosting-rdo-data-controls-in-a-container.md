---
title: "컨테이너에서 RDO 데이터 컨트롤을 호스팅하기 위한 모델 | Microsoft Docs"
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
  - "RDO RemoteData 컨트롤, 호스팅 모델"
  - "RemoteData 컨트롤, 호스팅 모델"
ms.assetid: ca598bac-9fef-40e6-b6cd-03d817e16b2e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컨테이너에서 RDO 데이터 컨트롤을 호스팅하기 위한 모델
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨테이너는 다음과 같이 RDO 데이터 컨트롤을 호스팅합니다.  
  
-   컨테이너가 데이터 컨트롤에서 IVBDSC 인터페이스를 가져옵니다.  IVBDSC를 찾지 못하면 데이터 컨트롤이 아닙니다.  
  
-   컨테이너가 데이터 컨트롤에서 **ICursor** 인터페이스를 가져옵니다.  이러한 인터페이스는 클라이언트가 조작할 수 있는 Cursor 개체를 제공합니다.  
  
-   컨테이너가 데이터 컨트롤의 **INotifyDBEvents** 인터페이스에 후크합니다.  이 인터페이스는 컨테이너가 데이터 컨트롤로부터 알림을 받을 수 있도록 합니다.  알림을 받을려면 컨테이너가 **INotifyDBEventsSink** 인터페이스를 지원해야 합니다.  
  
 컨테이너는 다음과 같이 RDO 데이터 바인딩 컨트롤을 호스팅합니다.  
  
-   컨트롤은 **IBoundObject** 인터페이스를 지원하고 컨테이너는 **IBoundObjectSite** 인터페이스를 지원합니다.  컨트롤은 컨테이너의 **IBoundObjectSite** 인터페이스를 가져오고, 컨테이너는 컨트롤에서 **IBoundObject** 인터페이스를 가져옵니다.  
  
-   컨트롤은 **IPropNotifySink** 인터페이스를 지원하고 컨테이너로 후크합니다.  이렇게 하면 컨테이너는 컨트롤로부터 알림을 받을 수 있습니다.  
  
-   컨트롤이 **INotifyDBEventsSink**를 지원하면 데이터 컨트롤의 **INotifyDBEvents** 인터페이스와 연결한 후 RDO 데이터 컨트롤로부터 알림을 받을 수 있습니다.  
  
-   그런 다음 컨트롤은 데이터 컨트롤에서 직접 또는 컨테이너를 통해 커서 개체를 받을 수 있으며,  커서를 조작하고 스크롤할 수 있습니다.  그러면 RDO 데이터 바인딩 컨트롤이 성공적으로 바인딩된 것입니다.  
  
## 참고 항목  
 [RDO 데이터 바인딩](../../data/ado-rdo/rdo-databinding.md)   
 [Visual C\+\+에서 RDO 데이터 바인딩 사용](../../data/ado-rdo/using-rdo-databinding-in-visual-cpp.md)