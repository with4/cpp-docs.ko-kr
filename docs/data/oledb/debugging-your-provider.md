---
title: "공급자 디버깅 | Microsoft Docs"
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
  - "디버깅[C++], 공급자"
  - "OLE DB 공급자, 디버깅"
  - "Visual C++ 디버거"
  - "Visual C++ 디버거, 공급자 디버깅"
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 공급자 디버깅
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 두 방법으로 공급자를 디버깅할 수 있습니다.  
  
-   공급자는 단계별로 만들어지므로 OLE DB 소비자 템플릿을 사용하여 일부 소비자 코드를 만든 다음 공급자 단계를 정상적으로 진행할 수 있습니다.  
  
-   Visual C\+\+에 제공되는 ITEST 유틸리티를 사용할 수 있습니다.  
  
### ITEST 유틸리티를 사용하려면  
  
1.  프로젝트를 엽니다.  
  
2.  **프로젝트** 메뉴에서 **설정**을 클릭합니다.  
  
3.  **속성 페이지** 대화 상자에서 **디버그** 탭을 클릭합니다.  
  
4.  **디버그 세션에 사용할 실행 파일** 상자에서 ITEST 응용 프로그램을 선택합니다.  
  
5.  중단점을 설정하고 디버깅합니다.  
  
## 참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)