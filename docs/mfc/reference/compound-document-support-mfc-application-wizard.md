---
title: "MFC 응용 프로그램 마법사, 복합 문서 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.compdoc"
dev_langs: 
  - "C++"
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# MFC 응용 프로그램 마법사, 복합 문서 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 응용 프로그램 마법사의 이 페이지에서는 응용 프로그램에서 제공하는 복합 문서 및 액티브 문서에 대한 지원 수준을 지정합니다.  복합 문서 및 문서 템플릿을 지원하려면 응용 프로그램에서 문서\/뷰 아키텍처를 지원해야 합니다.  
  
 기본적으로 응용 프로그램은 복합 문서를 지원하지 않습니다.  이 기본값을 그대로 사용하면 응용 프로그램에서 액티브 문서 또는 복합 파일을 지원하지 않게 됩니다.  
  
 **복합 문서 지원**  
 응용 프로그램에서 컨테이너 지원, 서버 지원 또는 두 가지 모두를 제공할 것인지 여부를 지정합니다.  자세한 내용은 다음을 참조하십시오.  
  
-   [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md)  
  
-   [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)  
  
|옵션|설명|  
|--------|--------|  
|**없음**|OLE\(Object Linking and Embedding\)를 지원하지 않음을 나타냅니다.  기본적으로 응용 프로그램 마법사에서는 ActiveX 지원을 포함하지 않은 채 응용 프로그램을 만듭니다.|  
|**컨테이너**|연결 개체와 포함 개체를 포함합니다.|  
|**미니 서버**|응용 프로그램에서 복합 문서 개체를 만들고 관리할 수 있음을 나타냅니다.  미니 서버는 독립적으로 실행될 수 없고 포함 항목만 지원합니다.|  
|**풀 서버**|응용 프로그램에서 복합 문서 개체를 만들고 관리할 수 있음을 나타냅니다.  풀 서버는 독립적으로 실행될 수 있으며 연결 항목과 포함 항목을 모두 지원합니다.|  
|**컨테이너\/풀 서버**|응용 프로그램은 컨테이너인 동시에 서버가 될 수 있음을 나타냅니다.  컨테이너는 자체 문서 내에 포함 항목이나 연결 항목을 통합할 수 있는 응용 프로그램입니다.  서버는 컨테이너 응용 프로그램에서 사용하는 자동화 항목을 만들 수 있는 응용 프로그램입니다.|  
  
 **추가 옵션**  
 응용 프로그램이 액티브 문서를 지원할지 여부를 지정합니다.  이 기능에 대한 자세한 내용은 [액티브 문서](../../mfc/active-documents.md)를 참조하십시오.  
  
|옵션|설명|  
|--------|--------|  
|**액티브 문서 서버\(A\)**|응용 프로그램에서 액티브 문서를 만들고 관리할 수 있음을 나타냅니다.  이 옵션을 선택하면 마법사의 [문서 템플릿 문자열](../../mfc/reference/document-template-strings-mfc-application-wizard.md) 페이지에서 **파일 확장명** 상자에 액티브 문서 서버에 대한 파일 확장명을 지정해야 합니다.  자세한 내용은 [액티브 문서 서버](../../mfc/active-document-servers.md)를 참조하십시오.|  
|**액티브 문서 컨테이너**|응용 프로그램의 프레임 내에 액티브 문서를 포함할 수 있음을 나타냅니다.  액티브 문서에는 Internet Explorer 문서 또는 Microsoft Word 파일이나 Excel 스프레드시트와 같은 Office 문서가 포함됩니다.  자세한 내용은 [액티브 문서 포함](../../mfc/active-document-containment.md)을 참조하십시오.|  
|**복합 파일 지원\(U\)**|복합 파일 형식을 사용하여 컨테이너 응용 프로그램의 문서를 serialize하지 않습니다.  이 옵션을 선택하면 개체를 포함하는 전체 파일이 메모리에 강제로 로드됩니다.  개벌 개체에 대해 증분 저장을 사용할 수 없습니다.  한 개체를 변경한 후에 저장하면 해당 파일에 있는 모든 개체가 저장됩니다.|  
  
## 참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)