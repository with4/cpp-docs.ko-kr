---
title: "CDocTemplate Class | Microsoft Docs"
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
  - "CDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocTemplate class"
  - "문서 템플릿"
  - "템플릿, 문서"
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문서 템플릿에 대 한 기본 기능을 정의 하는 추상 기본 클래스입니다.  
  
## 구문  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDocTemplate::CDocTemplate](../Topic/CDocTemplate::CDocTemplate.md)|`CDocTemplate` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDocTemplate::AddDocument](../Topic/CDocTemplate::AddDocument.md)|문서 서식 파일에 추가합니다.|  
|[CDocTemplate::CloseAllDocuments](../Topic/CDocTemplate::CloseAllDocuments.md)|이 서식 파일에 연결 된 모든 문서를 닫습니다.|  
|[CDocTemplate::CreateNewDocument](../Topic/CDocTemplate::CreateNewDocument.md)|새 문서를 만듭니다.|  
|[CDocTemplate::CreateNewFrame](../Topic/CDocTemplate::CreateNewFrame.md)|문서와 뷰를 포함 하는 새 프레임 창을 만듭니다.|  
|[CDocTemplate::CreateOleFrame](../Topic/CDocTemplate::CreateOleFrame.md)|있는 OLE 사용 가능 프레임 창을 만듭니다.|  
|[CDocTemplate::CreatePreviewFrame](../Topic/CDocTemplate::CreatePreviewFrame.md)|고급 미리 보기를 사용 하는 자식 프레임을 만듭니다.|  
|[CDocTemplate::GetDocString](../Topic/CDocTemplate::GetDocString.md)|문서 형식과 관련 된 문자열을 검색 합니다.|  
|[CDocTemplate::GetFirstDocPosition](../Topic/CDocTemplate::GetFirstDocPosition.md)|이 템플릿과 연결 된 첫 번째 문서의 위치를 검색 합니다.|  
|[CDocTemplate::GetNextDoc](../Topic/CDocTemplate::GetNextDoc.md)|문서 및 다음의 위치를 검색합니다.|  
|[CDocTemplate::InitialUpdateFrame](../Topic/CDocTemplate::InitialUpdateFrame.md)|프레임 창, 초기화 하 고 필요에 따라 표시 됩니다.|  
|[CDocTemplate::LoadTemplate](../Topic/CDocTemplate::LoadTemplate.md)|리소스에 대 한 로드를 주어진 `CDocTemplate` 파생 클래스.|  
|[CDocTemplate::MatchDocType](../Topic/CDocTemplate::MatchDocType.md)|일치 하는 문서 형식과이 템플릿 간의 신뢰의 정도 결정합니다.|  
|[CDocTemplate::OpenDocumentFile](../Topic/CDocTemplate::OpenDocumentFile.md)|경로 이름으로 지정 된 파일을 엽니다.|  
|[CDocTemplate::RemoveDocument](../Topic/CDocTemplate::RemoveDocument.md)|문서 서식 파일에서 제거합니다.|  
|[CDocTemplate::SaveAllModified](../Topic/CDocTemplate::SaveAllModified.md)|수정 된이 서식 파일과 관련 된 모든 문서를 저장 합니다.|  
|[CDocTemplate::SetContainerInfo](../Topic/CDocTemplate::SetContainerInfo.md)|현재 위치에서 OLE 항목을 편집할 때 OLE 컨테이너에 대 한 리소스를 결정 합니다.|  
|[CDocTemplate::SetDefaultTitle](../Topic/CDocTemplate::SetDefaultTitle.md)|이 제목은 문서 윈도우의 제목 표시줄에 표시 됩니다.|  
|[CDocTemplate::SetPreviewInfo](../Topic/CDocTemplate::SetPreviewInfo.md)|프로세스 미리 보기 처리기를 설치 합니다.|  
|[CDocTemplate::SetServerInfo](../Topic/CDocTemplate::SetServerInfo.md)|서버 문서에 포함 된 또는 현재 위치에서 편집할 때 리소스 및 클래스를 결정 합니다.|  
  
## 설명  
 일반적으로 하나 이상의 문서 템플릿은 응용 프로그램의 구현에 만든 `InitInstance` 함수입니다.  문서 서식 파일은 세 가지 형식의 클래스 간의 관계를 정의합니다.  
  
-   문서 클래스에서 파생 되는  **CDocument**.  
  
-   뷰 클래스 위에 나열 된 문서 클래스에서 데이터를 표시 합니다.  You can derive this class from `CView`, `CScrollView`, `CFormView`, or `CEditView`.  \(또한 수 `CEditView` 직접 합니다.\)  
  
-   보기를 포함 하는 프레임 창 클래스  단일 문서 인터페이스 \(SDI\) 응용 프로그램의 경우이 클래스에서 파생 될 `CFrameWnd`.  다중 문서 인터페이스 \(MDI\) 응용에 대해이 클래스에서 파생 될 `CMDIChildWnd`.  프레임 창의 동작을 사용자 지정 하지 않아도 수 `CFrameWnd` 또는 `CMDIChildWnd` 고유한 클래스를 파생 하지 않고 직접.  
  
 응용 프로그램이 각 지 원하는 문서 형식에 대 한 문서 템플릿이 있습니다.  예를 들어, 스프레드시트 및 텍스트 문서를 모두 지 원하는 응용 프로그램을 응용 프로그램에 두 문서 템플릿 개체 있습니다.  각 문서 템플릿을 만들고 해당 형식의 모든 문서 관리를 담당 합니다.  
  
 문서 서식 파일에 대 한 포인터를 저장 된 `CRuntimeClass` 문서, 뷰 및 프레임 창 클래스에 대 한 개체.  이러한 `CRuntimeClass` 개체는 문서 서식 파일을 만들 때 지정 됩니다.  
  
 문서 서식 파일 문서 종류 \(예: 메뉴, 아이콘, 액셀러레이터 키 테이블 리소스\)를 사용 하는 리소스의 ID를 포함 합니다.  문서 서식 파일의 문서 형식에 대 한 추가 정보를 포함 하는 문자열에도 있습니다.  이러한 이름을 파일 확장명 \(예: ".xls"\) 및 문서 형식 \(예: "워크시트"\)이 포함 됩니다.  선택적으로 사용 하는 응용 프로그램의 사용자 인터페이스, Windows 파일 관리자 및 개체 연결 및 포함 \(OLE\) 지원으로 다른 문자열이 포함 될 수 있습니다.  
  
 또한 문서 서식 파일 OLE 컨테이너 및\/또는 서버 응용 프로그램 일 경우 현재 위치에서 활성화 하는 동안 사용 되는 메뉴의 ID를 정의 합니다.  OLE 서버 응용 프로그램 일 경우, 문서 서식 파일 ID의 현재 위치에서 활성화 하는 동안 사용 되는 메뉴 및 도구 모음을 정의 합니다.  이러한 추가 OLE 리소스를 호출 하 여 지정한 `SetContainerInfo` 및 `SetServerInfo`.  
  
 때문에 `CDocTemplate` 추상 클래스인 클래스를 직접 사용할 수 없습니다.  일반적인 응용 프로그램 둘 중 하나를 사용 하 여 `CDocTemplate`\-Mfc 라이브러리에서 제공 하는 클래스를 파생: `CSingleDocTemplate`, SDI를 구현 및 `CMultiDocTemplate`, MDI를 구현 합니다.  문서 서식 파일을 사용 하 여 해당 클래스에 대 한 자세한 내용은 참조 하십시오.  
  
 SDI 또는 MDI에서 근본적으로 다른 것은 사용자 인터페이스 패러다임은 응용 프로그램에 필요한 경우 클래스에서 파생 될 수 있습니다 `CDocTemplate`.  
  
 에 대 한 자세한 내용은 `CDocTemplate`를 참조 하십시오  [문서 템플릿과 문서\/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CSingleDocTemplate Class](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate Class](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [CEditView Class](../../mfc/reference/ceditview-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)