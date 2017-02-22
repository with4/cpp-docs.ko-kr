---
title: "COleDocObjectItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDocObjectItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDocObjectItem class"
  - "containment"
  - "containment, doc object"
  - "doc object containment"
  - "document object containment"
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleDocObjectItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

액티브 문서 포함을 구현 합니다.  
  
## 구문  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDocObjectItem::COleDocObjectItem](../Topic/COleDocObjectItem::COleDocObjectItem.md)|생성 된 `COleDocObject` 항목.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDocObjectItem::DoDefaultPrinting](../Topic/COleDocObjectItem::DoDefaultPrinting.md)|기본 프린터 설정을 사용 하 여 컨테이너 응용 프로그램의 문서를 인쇄 합니다.|  
|[COleDocObjectItem::ExecCommand](../Topic/COleDocObjectItem::ExecCommand.md)|사용자가 지정한 명령을 실행 합니다.|  
|[COleDocObjectItem::GetActiveView](../Topic/COleDocObjectItem::GetActiveView.md)|현재 보기에서 문서를 검색합니다.|  
|[COleDocObjectItem::GetPageCount](../Topic/COleDocObjectItem::GetPageCount.md)|문서의 컨테이너 응용 프로그램의 페이지 수를 검색합니다.|  
|[COleDocObjectItem::OnPreparePrinting](../Topic/COleDocObjectItem::OnPreparePrinting.md)|컨테이너 응용 프로그램의 문서 인쇄를 준비합니다.|  
|[COleDocObjectItem::OnPrint](../Topic/COleDocObjectItem::OnPrint.md)|컨테이너 응용 프로그램의 문서를 인쇄합니다.|  
|[COleDocObjectItem::QueryCommand](../Topic/COleDocObjectItem::QueryCommand.md)|사용자 인터페이스 이벤트를 생성 하는 하나 이상의 명령의 상태를 쿼리 합니다.|  
|[COleDocObjectItem::Release](../Topic/COleDocObjectItem::Release.md)|OLE 항목을 연결 하는 연결 해제 하 고 열린 상태를 닫습니다.  클라이언트 항목은 삭제 되지 않습니다.|  
  
## 설명  
 MFC에서 액티브 문서는 일반, 현재 위치에서 편집 가능와 다음과 같은 차이점이 포함 비슷하게 처리 됩니다.  
  
-   `COleDocument`\-파생된 클래스 목록에 현재 포함 된 항목입니다; 여전히 유지. 그러나이 항목 수 `COleDocObjectItem`\-항목을 파생 합니다.  
  
-   액티브 문서 활성화 되 면 현재 위치에서 활성화 때 뷰의 전체 클라이언트 영역을 차지 합니다.  
  
-   액티브 문서 컨테이너는 모든 권한을 갖고 있는  **도움말** 메뉴.  
  
-   **도움말** 메뉴에 액티브 문서 컨테이너와 서버 메뉴 항목을 포함 합니다.  
  
 액티브 문서 컨테이너를 소유 하 고 있으므로  **도움말** 메뉴에서 컨테이너는 서버에 전달 해야  **도움말** 메시지를 서버 메뉴.  이 통합 처리 하 고 `COleDocObjectItem`.  
  
 메뉴 병합 및 액티브 문서 활성화에 대 한 자세한 내용은 개요를 참조 하십시오.  [액티브 문서 포함](../../mfc/active-document-containment.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [활성화](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [MFCBIND MFC 샘플](../../top/visual-cpp-samples.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem Class](../../mfc/reference/cdocobjectserveritem-class.md)