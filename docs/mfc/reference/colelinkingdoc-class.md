---
title: "COleLinkingDoc Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleLinkingDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinkingDoc class"
  - "OLE containers, client items"
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleLinkingDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 클래스에 포함 된 항목의 링크를 지 원하는 OLE 컨테이너 문서를 포함 합니다.  
  
## 구문  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleLinkingDoc::COleLinkingDoc](../Topic/COleLinkingDoc::COleLinkingDoc.md)|`COleLinkingDoc` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleLinkingDoc::Register](../Topic/COleLinkingDoc::Register.md)|문서는 OLE 시스템 Dll을 등록합니다.|  
|[COleLinkingDoc::Revoke](../Topic/COleLinkingDoc::Revoke.md)|문서의 등록을 해지합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleLinkingDoc::OnFindEmbeddedItem](../Topic/COleLinkingDoc::OnFindEmbeddedItem.md)|지정 된 포함 된 항목을 찾습니다.|  
|[COleLinkingDoc::OnGetLinkedItem](../Topic/COleLinkingDoc::OnGetLinkedItem.md)|지정한 연결 된 항목을 찾습니다.|  
  
## 설명  
 컨테이너 응용 프로그램에 포함 된 항목의 링크를 지 원하는 "연결 컨테이너" 라고 합니다. [OCLIENT](../../top/visual-cpp-samples.md) 샘플 응용 프로그램 링크가 컨테이너의 예입니다.  
  
 다른 문서에 포함 된 항목에 연결 된 항목의 소스 되 면 편집할 수 있도록 포함 된 항목을 포함 하는 문서 로드 되어야 합니다.  이러한 이유로 연결 컨테이너 컨테이너 응용 프로그램에서 다른 사용자가 원본 연결된 항목을 편집 하려고 할 때 시작할 수 있어야 합니다.  또한 응용 프로그램을 사용 해야는  [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) 클래스 프로그래밍 방식으로 시작 하는 경우 문서를 만들 수 있도록 합니다.  
  
 연결 컨테이너를 컨테이너를 확인 하려면 문서 클래스에서 파생 `COleLinkingDoc` 대신  [COleDocument](../../mfc/reference/coledocument-class.md).  모든 다른 OLE 컨테이너 처럼, 응용 프로그램의 네이티브 데이터는 물론 포함 되거나 연결 된 항목을 저장 하기 위한 클래스를 디자인 해야 합니다.  또한 원시 데이터를 저장 하기 위한 데이터 구조를 디자인 해야 합니다.  정의할 경우는 `CDocItem`\-파생 클래스 응용 프로그램은 네이티브의 대 한 데이터를 정의 하는 인터페이스 사용할 수 `COleDocument` 원시 데이터 뿐만 아니라 OLE 데이터를 저장 하.  
  
 응용 프로그램을 프로그래밍 방식으로 다른 컨테이너에서 시작 하는 선언 된 `COleTemplateServer` 개체의 응용 프로그램의 구성원으로 `CWinApp`\-파생 클래스:  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/CPP/colelinkingdoc-class_1.h)]  
  
 에 `InitInstance` 멤버 함수를 `CWinApp`\-클래스에서 파생 된 문서 서식 파일을 만들고 지정을 `COleLinkingDoc`\-문서 클래스에서 클래스를 파생:  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/CPP/colelinkingdoc-class_2.cpp)]  
  
 연결을 `COleTemplateServer` 개체에는 개체를 호출 하 여 문서 서식 파일 `ConnectTemplate` 멤버 함수 및 모든 클래스는 OLE 시스템으로 호출 하 여 개체 등록  **COleTemplateServer::RegisterAll**.  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/CPP/colelinkingdoc-class_3.cpp)]  
  
 샘플에 대 한 `CWinApp`\-파생 클래스 정의 및 `InitInstance` 작동, OCLIENT 참조 하십시오.H 및 OCLIENT입니다.CPP MFC 샘플에서  [OCLIENT](../../top/visual-cpp-samples.md).  
  
 사용에 대 한 자세한 내용은 `COleLinkingDoc`, 문서를 참조 하십시오.  [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md) 및  [컨테이너: 고급 기능](../../mfc/containers-advanced-features.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [MFC 샘플 OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)