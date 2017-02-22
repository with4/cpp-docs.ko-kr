---
title: "CSingleDocTemplate Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSingleDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleDocTemplate class"
  - "문서 템플릿, single"
  - "SDI(단일 문서 인터페이스), 응용 프로그램"
  - "템플릿, SDI"
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSingleDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단일 문서 인터페이스 \(SDI\)를 구현 하는 문서 서식 파일을 정의 합니다.  
  
## 구문  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSingleDocTemplate::CSingleDocTemplate](../Topic/CSingleDocTemplate::CSingleDocTemplate.md)|`CSingleDocTemplate` 개체를 생성합니다.|  
  
## 설명  
 SDI 응용 프로그램 주 프레임 창 사용 하 여 문서를 표시 합니다. 문서를 한 번에 열 수 있습니다.  
  
 문서 템플릿 세 가지 형식의 클래스 간의 관계를 정의합니다.  
  
-   문서 클래스에서 파생 되는  **CDocument**.  
  
-   뷰 클래스 위에 나열 된 문서 클래스에서 데이터를 표시 합니다.  You can derive this class from `CView`, `CScrollView`, `CFormView`, or `CEditView`.  \(또한 수 `CEditView` 직접 합니다.\)  
  
-   보기를 포함 하는 프레임 창 클래스  SDI 문서 서식 파일에 대해이 클래스에서 파생 될 수 있습니다 `CFrameWnd`. 주 프레임 창의 동작을 사용자 지정 해야 하는 경우 사용할 수 있습니다 `CFrameWnd` 고유한 클래스를 파생 하지 않고 직접.  
  
 하나만 있으므로 일반적으로 SDI 응용 프로그램 문서를 지 원하는 `CSingleDocTemplate` 개체입니다.  문서를 한 번에 열 수 있습니다.  
  
 모든 멤버 함수를 호출할 필요가 `CSingleDocTemplate` 생성자를 제외 하 고.  프레임 워크 핸들 `CSingleDocTemplate` 개체를 내부적으로.  
  
 사용에 대 한 자세한 내용은 `CSingleDocTemplate`를 참조 하십시오  [문서 템플릿과 문서\/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [만드는](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [DOCKTOOL MFC 샘플](../../top/visual-cpp-samples.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate Class](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)