---
title: "MFC 클래스 추가 마법사, 문서 템플릿 문자열 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.mfc.simple.doctemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC 클래스 추가 마법사, 문서 컨트롤 문자열"
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# MFC 클래스 추가 마법사, 문서 템플릿 문자열
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

마법사의 이 페이지는 다음 조건에 맞는 클래스에만 사용할 수 있습니다.  
  
-   MFC 프로젝트에서 문서\/뷰 아키텍처를 지원하는 경우  
  
-   새 클래스의 기본 클래스가 [CFormView](../../mfc/reference/cformview-class.md)인 경우  
  
-   [MFC 클래스 마법사](../../mfc/reference/mfc-add-class-wizard.md)의 **이름** 섹션에서 **DocTemplate 리소스 생성** 확인란이 선택된 경우  
  
 이 마법사에서는 폼 뷰 디자인, 관리 및 지역화에 도움을 주기 위해 다음 값에 대한 기본값을 제공합니다.  대부분의 문서 템플릿 문자열은 폼 사용자가 보고 사용할 수 있으므로 프로젝트를 만들 때 MFC 응용 프로그램 마법사의 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 페이지에 표시된 **리소스 언어**로 지역화됩니다.  
  
> [!NOTE]
>  이 마법사에서는 `CFormView`에서 파생된 클래스에 대해 자동 인쇄 지원을 제공하지 않습니다.  
  
 자세한 내용은 [문서 템플릿과 문서\/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md)를 참조하십시오.  
  
## 지역화되지 않은 문자열  
 이 옵션은 사용자 문서를 만드는 응용 프로그램에 적용됩니다.  문서 형식에 파일 확장명과 파일 형식 ID가 포함되어 있으면 문서를 더 쉽게 열고 저장할 수 있습니다.  이러한 항목은 사용자가 아니라 시스템에서 사용하므로 지역화되지 않습니다.  
  
 **파일 확장명**  
 이 폼 응용 프로그램의 문서 형식과 관련된 파일 확장명을 설정합니다.  파일 확장명은 클래스 이름을 기본으로 합니다.  예를 들어, 새 MFC 클래스 이름이 **Cwidget**일 경우 파일 확장명은 기본적으로 .wid가 됩니다.  파일 확장명은 파일 필터와 **열기** 및 **다른 이름으로 저장** 대화 상자에서 사용됩니다.  
  
 파일 확장명을 변경하면 **필터 이름** 상자에 변경 내용이 반영됩니다.  
  
> [!NOTE]
>  기본 파일 확장명을 변경하는 경우 마침표를 포함하지 마십시오.  
  
 **파일 형식 ID**  
 시스템 레지스트리의 문서 형식에 대한 레이블을 설정합니다.  
  
## 지역화된 문자열  
 응용 프로그램 사용자가 읽고 사용하는 폼 및 문서와 연관된 문자열을 생성합니다. 따라서 이 문자열은 지역화됩니다.  
  
 **문서 형식 이름**  
 응용 프로그램의 문서를 그룹화할 수 있는 문서 형식을 식별합니다.  기본적으로, 문서 형식 이름은 클래스 이름을 기본으로 합니다.  예를 들어, 새 MFC 클래스 이름이 **Cwidget**이면 문서 형식 이름은 기본적으로 Widget가 됩니다.  기본값을 변경해도 이 대화 상자의 다른 옵션은 바뀌지 않습니다.  
  
 **필터 이름**  
 지정한 파일 형식의 파일을 찾기 위해 사용자가 지정할 수 있는 이름을 설정합니다.  이 옵션은 표준 Windows **열기** 대화 상자의 **파일 형식** 옵션과 **다른 이름으로 저장** 대화 상자의 **파일 형식** 옵션에서 사용할 수 있습니다.  기본적으로 프로젝트 이름에 Files를 추가하고 **파일 확장명**에 지정된 확장명을 뒤에 붙여 이 이름이 지정됩니다.  예를 들어, 프로젝트 이름이 Widget이고 파일 확장명이 .wid일 경우 **필터 이름**은 기본적으로 Widget Files\(\*.wid\)가 됩니다.  
  
 **파일의 새 약식 이름**  
 프로젝트에 둘 이상의 문서 템플릿이 있을 경우 표준 Windows **새로 만들기** 대화 상자에 나타나는 이름을 설정합니다.  응용 프로그램이 [자동화 서버](../../mfc/automation-servers.md)이면 이 이름은 자동화 개체의 약식 이름으로 사용됩니다.  기본적으로 이 이름은 클래스 이름을 기본으로 합니다.  
  
 **파일 형식의 긴 이름**  
 시스템 레지스트리의 파일 형식 이름을 설정합니다.  응용 프로그램이 자동화 서버인 경우 이 이름을 자동화 개체의 긴 이름으로 사용합니다.  기본적으로 이 이름은 클래스 이름에 .Document를 추가하여 지정합니다.  예를 들어, 클래스 이름이 **Cwidget**일 경우 **파일 형식의 긴 이름**은 Widget Document가 됩니다.  
  
 **문서 클래스**  
 프로젝트의 문서 클래스를 지정합니다.  기본적으로 이 클래스는 MFC 응용 프로그램 마법사의 [생성된 클래스 검토](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지에 나열된 주 응용 프로그램의 문서 클래스입니다.  프로젝트에 다른 문서 클래스를 추가한 경우 목록에서 다른 문서 클래스를 선택할 수 있습니다.  
  
## 참고 항목  
 [MFC 클래스 추가 마법사](../../mfc/reference/mfc-add-class-wizard.md)   
 [MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)