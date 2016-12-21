---
title: "OLE 컨테이너 클래스 | Microsoft Docs"
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
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 클래스[C++]"
  - "컨테이너 클래스[C++]"
  - "컨테이너[C++], OLE 컨테이너 응용 프로그램"
  - "OLE[C++], 클래스"
  - "OLE 클래스[C++]"
  - "비주얼 편집[C++], 클래스"
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE 컨테이너 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이러한 클래스들은 컨테이너 응용 프로그램에 의해 사용됩니다.  `COleLinkingDoc` 와 `COleDocument` 둘 모두 `COleClientItem` 개체들의 컬렉션을 관리합니다.  **CDocumnet**로부터 파생된 클래스보다, `COleLinkingDoc` 또는 `COleDocument` 로부터 이것을 파생할 것이고, 문서에서 포함된 개체에 대한 연결을 지원하길 원하는지의 여부에 따라 다릅니다.  
  
 다른 문서로 연결되거나 다른 문서로부터 포함된 문서에서 각 OLE 항목을 나타내기위해 `COleClientItem` 을 사용합니다.  
  
 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)  
 액티브 문서 포함을 지원합니다.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 기본 컨테이너 지원 뿐만 아니라 복합 문서 구현에도 사용됩니다.  `CDocItem` 로부터 파생되는 클래스에 대한 컨테이너를 제공합니다.  이 클래스는 컨테이너 문서에 대한 기본 클래스로써 사용될 수 있고 `COleServerDoc` 에 대한 기본 클래스입니다.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 연결에 대한 인프라를 제공하는 `COleDocument` 로부터 파생된 클래스입니다.  만일 포함된 개체들에 대한 연결을 지원하기 위하기를 원한다면, `COleDocument` 대신 이 클래스에서 컨테이너 응용프로그램의 문서 클래스를 파생시켜야 합니다.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 여러 편집 컨트롤에 있는 OLE 클라이언트 항목들의 목록을 유지 관리합니다.  [CRichEditView](../mfc/reference/cricheditview-class.md) 와 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md) 을 함께 사용합니다.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 `COleClientItem` 와 `COleServerItem` 의 추상 기본 클래스입니다.  문서의 부분을 나타내는 `CDocItem` 로부터 파생된 클래스들의 개체들입니다.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 OLE 항목에 연결되거나 포함된 연결의 클라이언트 부분을 나타내는 클라이언트 항목 클래스입니다.  이 클래스로부터 클라이언트 항목들이 파생됩니다.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 `CRichEditView` 와 `CRichEditDoc` 를 함께 사용할 때, 여러 편집 컨트롤에서 저장된 OLE 항목에 대해 클라이언트 액세스를 제공합니다.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE 처리 과정에서 오류가 발생한 예외입니다.  이 클래스는 컨테이너와 서버, 두가지 모두 사용됩니다.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)