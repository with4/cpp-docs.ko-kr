---
title: "ActiveX 컨트롤 컨테이너: 컨트롤 속성 보기 및 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤 컨테이너[C++], 속성 보기 및 수정"
  - "ActiveX 컨트롤[C++], 속성"
  - "컨트롤[MFC], 속성"
  - "속성[MFC], 보기 및 수정"
  - "리소스 편집기, ActiveX 컨트롤 보기 및 수정"
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX 컨트롤 컨테이너: 컨트롤 속성 보기 및 수정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트에 ActiveX 컨트롤을 삽입했을 때, ActiveX 컨트롤에 의해 지원된 속성을 보거나 바꾸는 것이 유용합니다.  이 문서는 이 작업을 수행하기 위해 Visual C\+\+ 리소스 편집기를 사용하는 방법을 설명합니다.  
  
 ActiveX 컨트롤 컨테이너 응용 프로그램이 포함된 컨트롤을 사용하면, 리소스 편집기에서 컨트롤의 속성을 보거나 수정할 수 있습니다.  또한 설계 시간 동안 속성 값을 설정하기 위해서 리소스 편집기를 사용할 수 있습니다.  그때 리소스 편집기는 프로젝트의 리소스 파일에 이러한 값을 자동적으로 저장합니다.  그때 컨트롤의 모든 인스턴스는 이러한 값으로 초기화된 그것의 속성을 가질 것입니다.  
  
 이 절차는 사용자가 컨트롤을 사용자 프로젝트에 삽입했다고 가정합니다.  자세한 내용은 [ActiveX Control Containers: Inserting a Control Into a Control Container Application](../mfc/inserting-a-control-into-a-control-container-application.md)을 참조하십시오.  
  
 컨트롤의 속성을 확인 하는 첫 번째 단계는 컨트롤의 인스턴스를 프로젝트 대화 상자 템플릿에 추가하는 것입니다.  
  
### 컨트롤의 속성을 보려면  
  
1.  리소스 뷰에서, **Dialog** 폴더를 엽니다.  
  
2.  주 대화 상자 템플릿을 엽니다.  
  
3.  **Insert ActiveX Control** 대화 상자를 사용하여 ActiveX 컨트롤을 삽입합니다.  자세한 내용은 [Viewing and Adding ActiveX Controls to a Dialog Box](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md)를 참조하십시오.  
  
4.  대화 상자에서 ActiveX 컨트롤을 선택합니다.  
  
5.  속성 창에서 **속성** 단추를 클릭합니다.  
  
 새로운 속성을 즉시 수정하거나 테스트하기 위해 **Properites** 대화 상자를 사용합니다.  
  
## 참고 항목  
 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)