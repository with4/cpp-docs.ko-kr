---
title: "MFC ActiveX 컨트롤 마법사, 컨트롤 이름 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.names"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX 컨트롤 마법사, 컨트롤 이름"
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MFC ActiveX 컨트롤 마법사, 컨트롤 이름
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨트롤 클래스와 속성 페이지 클래스 이름, 형식 이름 및 컨트롤의 형식 식별자를 지정합니다.  **약식 이름**을 제외한 모든 필드는 독립적으로 편집할 수 있습니다.  **약식 이름**의 텍스트를 변경하면 변경 내용은 이 페이지의 다른 모든 필드 이름에 반영됩니다.  이 명명 작업은 컨트롤을 개발할 때 모든 이름을 쉽게 식별할 수 있도록 하기 위한 것입니다.  
  
 **약식 이름**  
 컨트롤의 약식 이름을 제공합니다.  기본적으로 이 이름은 **새 프로젝트** 대화 상자에서 제공한 프로젝트 이름을 기반으로 하여 지정됩니다.  해당 필드를 개별적으로 변경하지 않으면 제공한 이름에 따라 클래스 이름, 형식 이름 및 형식 식별자가 결정됩니다.  
  
 **컨트롤 클래스 이름**  
 기본적으로 컨트롤 클래스의 이름은 약식 이름 앞에 `C`를 붙이고 뒤에는 `Ctrl`을 붙입니다.  예를 들어, 컨트롤의 약식 이름이 `Price`이면 컨트롤 클래스 이름은 `CPriceCtrl`입니다.  
  
 **컨트롤 .h 파일**  
 기본적으로 헤더 파일의 이름은 약식 이름 뒤에 `Ctrl`을 붙이고 파일 이름 확장명 `.h`를 붙입니다.  예를 들어, 컨트롤의 약식 이름이 `Price`이면 헤더 파일 이름은 `PriceCtrl.h`입니다.  이 필드의 이름은 컨트롤 클래스 이름과 일치해야 합니다.  
  
 **컨트롤 .cpp 파일**  
 기본적으로 헤더 파일의 이름은 약식 이름 뒤에 `Ctrl`을 붙이고 파일 이름 확장명 `.cpp`를 붙입니다.  예를 들어, 컨트롤의 약식 이름이 `Price`이면 헤더 파일 이름은 `PriceCtrl.cpp`입니다.  이 필드의 이름은 헤더 이름과 일치해야 합니다.  
  
 **컨트롤 형식 이름**  
 기본적으로 컨트롤 형식의 이름은 약식 이름 다음에 `Control`이 옵니다.  예를 들어, 컨트롤의 약식 이름이 `Price`이면 컨트롤 클래스 형식 이름은 `Price Control`입니다.  이 필드의 값을 변경할 경우에는 이름이 상속을 나타내도록 해야 합니다.  
  
 **컨트롤 형식 ID**  
 컨트롤 클래스의 컨트롤 형식 ID를 설정합니다.  컨트롤은 프로젝트에 추가될 때 이 문자열을 레지스트리에 기록합니다.  컨테이너 응용 프로그램에서는 이 문자열을 사용하여 컨트롤 인스턴스를 만듭니다.  
  
 기본적으로 컨트롤 형식 ID는 **새 프로젝트** 대화 상자에서 지정한 프로젝트 이름과 약식 이름을 기반으로 합니다.  이 이름은 형식 이름과 일치해야 합니다.  
  
 기본적으로 컨트롤 형식 ID는 다음과 같이 표시됩니다.  
  
 *ProjectName*.*ShortName*Ctrl.1  
  
 이 대화 상자에서 약식 이름을 변경하면 컨트롤 형식 ID는 다음과 같이 표시됩니다.  
  
 *ProjectName*.*NewShortName*Ctrl.1  
  
 **속성 페이지 클래스 이름**  
 기본적으로 속성 페이지 클래스의 이름은 약식 이름 앞에 `C`를 붙이고 뒤에 `PropPage`를 붙입니다.  예를 들어, 컨트롤의 약식 이름이 `Price`이면 속성 페이지 클래스 이름은 `CPricePropPage`입니다.  이 이름은 컨트롤 클래스 이름에 `PropPage`를 추가한 것과 일치해야 합니다.  
  
 **속성 페이지 .h 파일**  
 기본적으로 속성 페이지 헤더 파일의 이름은 약식 이름 뒤에 `PropPage`를 붙이고 파일 확장명 `.h`를 붙입니다.  예를 들어, 컨트롤의 약식 이름이 `Price`이면 속성 페이지 헤더 파일 이름은 `PricePropPage.h`입니다.  이 이름은 클래스 이름과 일치해야 합니다.  
  
 **속성 페이지 .cpp 파일**  
 기본적으로 속성 페이지 구현 파일의 이름은 약식 이름 뒤에 `PropPage`를 붙이고 파일 확장명 `.cpp`를 붙입니다.  예를 들어, 컨트롤의 약식 이름이 `Price`이면 속성 페이지 헤더 파일 이름은 `PricePropPage.cpp`입니다.  이 이름은 헤더 파일 이름과 일치해야 합니다.  
  
 **속성 페이지 형식 이름**  
 기본적으로 속성 페이지 형식 이름은 약식 이름 다음에 `Property Page`를 붙입니다.  예를 들어, 컨트롤의 약식 이름이 `Price`이면 속성 페이지 형식 이름은 `Price Property Page`입니다.  이 필드의 값을 변경할 경우에는 이름이 컨트롤 클래스를 나타내도록 해야 합니다.  
  
 **속성 페이지 ID**  
 속성 페이지 클래스의 ID를 설정합니다.  컨트롤은 프로젝트에 적용될 때 이 문자열을 레지스트리에 기록합니다.  컨테이너 응용 프로그램에서는 이 문자열을 사용하여 컨트롤 속성 페이지의 인스턴스를 만듭니다.  
  
 기본적으로 속성 페이지 형식 ID는 **새 프로젝트** 대화 상자에서 지정한 프로젝트 이름과 약식 이름을 기반으로 합니다.  이 이름은 형식 이름과 일치해야 합니다.  
  
 기본적으로 속성 페이지 형식 ID는 다음과 같이 표시됩니다.  
  
 *ProjectName*.*ShortName*PropPage.1  
  
 이 대화 상자에서 약식 이름을 변경하면 속성 페이지 형식 ID는 다음과 같이 표시됩니다.  
  
 *ProjectName*.*NewShortName*PropPage.1  
  
## 참고 항목  
 [MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)   
 [응용 프로그램 설정, MFC ActiveX 컨트롤 마법사](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [MFC ActiveX 컨트롤 마법사, 컨트롤 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)   
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)