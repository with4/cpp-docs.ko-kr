---
title: "CMultiPageDHtmlDialog Class | Microsoft Docs"
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
  - "CMultiPageDHtmlDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPageDHtmlDialog class"
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiPageDHtmlDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여러 페이지로 구성 된 대화 상자 순차적으로 여러 HTML 페이지를 표시 하 고 각 페이지에서 이벤트 처리.  
  
## 구문  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog.md)|여러 페이지 \(마법사 스타일\) DHTML dialog 개체를 만듭니다.|  
|[CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog.md)|여러 페이지로 된 DHTML dialog 개체를 소멸 시킵니다.|  
  
## 설명  
 이 작업을 수행 하는 메커니즘입니다는  [URL 및 DHTML 이벤트 맵](http://msdn.microsoft.com/ko-kr/2a7332f0-79d7-46e4-b816-0a618c46777a), 포함 된  [포함 된 이벤트 맵](../Topic/BEGIN_EMBED_DHTML_EVENT_MAP.md) 각 페이지에 대 한.  
  
## 예제  
 간단한 마법사와 비슷한 기능을 정의 하는 HTML 리소스 세이 여러 페이지로 구성 된 대화 상자를 가정 합니다.  첫 페이지는 `Next` 단추, 두 번째는  **이전** 및 `Next` 단추 및 세 번째는  **이전** 단추.  처리기 함수를 호출 하는 단추 중 하나를 누를 때  [CDHtmlDialog::LoadFromResource](../Topic/CDHtmlDialog::LoadFromResource.md) 적절 한 새 페이지를 로드 합니다.  
  
 클래스 선언 \(CMyMultiPageDlg.h\)에 관련 된 부분:  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/CPP/cmultipagedhtmldialog-class_1.h)]  
  
 클래스 구현 \(CMyMultipageDlg.cpp\)에 관련 된 부분:  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/CPP/cmultipagedhtmldialog-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## 요구 사항  
 **헤더:** afxdhtml.h  
  
## 참고 항목  
 [CDHtmlDialog Class](../../mfc/reference/cdhtmldialog-class.md)   
 [Multipage DHTML and URL Event Maps \(NIB\)](http://msdn.microsoft.com/ko-kr/2a7332f0-79d7-46e4-b816-0a618c46777a)