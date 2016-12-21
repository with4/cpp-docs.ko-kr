---
title: "CMultiDocTemplate Class | Microsoft Docs"
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
  - "CMultiDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiDocTemplate class"
  - "MDI, 템플릿"
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다중 문서 인터페이스 \(MDI\)를 구현 하는 문서 서식 파일을 정의 합니다.  
  
## 구문  
  
```  
  
class CMultiDocTemplate : public CDocTemplate  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMultiDocTemplate::CMultiDocTemplate](../Topic/CMultiDocTemplate::CMultiDocTemplate.md)|`CMultiDocTemplate` 개체를 생성합니다.|  
  
## 설명  
 MDI 응용 프로그램의 주 프레임 창을 각각 문서를 표시 합니다. 사용자는 0 개 이상의 문서 프레임 창을 열어도 공간으로 사용 합니다.  MDI에 대 한 자세한 설명은 참조 하십시오.  *소프트웨어 디자인에 대 한 Windows 인터페이스 지침*.  
  
 문서 서식 파일은 세 가지 형식의 클래스 간의 관계를 정의합니다.  
  
-   문서 클래스에서 파생 되는  [CDocument](../../mfc/reference/cdocument-class.md).  
  
-   뷰 클래스 위에 나열 된 문서 클래스에서 데이터를 표시 합니다.  이 클래스에서 파생 될 수 있습니다  [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, 또는 `CEditView`.  \(또한 수 `CEditView` 직접 합니다.\)  
  
-   보기를 포함 하는 프레임 창 클래스  MDI 문서 서식 파일에 대해이 클래스에서 파생 될 수 있습니다 `CMDIChildWnd`, 또는 문서 프레임 창의 동작을 사용자 지정 하지 않아도 사용할 수 있습니다  [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 고유한 클래스를 파생 하지 않고 직접.  
  
 MDI 응용 프로그램에 둘 이상의 문서 형식을 지원할 수와 동시에 다양 한 종류의 문서를 열 수 있습니다.  응용 프로그램에서 지 원하는 각 문서 형식에 문서 서식 파일을 하나 있습니다.  MDI 응용 프로그램에 스프레드시트 및 텍스트 문서를 모두 지 원하는 경우 예를 들어, 응용 프로그램이 두 개의 `CMultiDocTemplate` 개체입니다.  
  
 새 문서를 만들면 응용 프로그램의 문서 템플릿을 사용 합니다.  응용 프로그램 두 개 이상의 문서 형식을 지 원하는 프레임 워크 문서 서식 파일에서 지원 되는 문서 유형의 이름을 가져옵니다 및 새 파일 대화 상자에서 목록에 표시 합니다.  사용자가 문서 종류를 선택한 후 응용 프로그램 문서 클래스 개체, 프레임 창 개체를 뷰 개체를 만듭니다 및를 서로 연결 합니다.  
  
 멤버 함수를 호출 하지 않아도 `CMultiDocTemplate` 생성자를 제외 하 고.  프레임 워크 핸들 `CMultiDocTemplate` 개체를 내부적으로.  
  
 에 대 한 자세한 내용은 `CMultiDocTemplate`를 참조 하십시오  [문서 템플릿과 문서\/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [만드는](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate Class](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)