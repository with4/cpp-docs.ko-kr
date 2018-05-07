---
title: 컨트롤 이름, MFC ActiveX 컨트롤 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.ctl.names
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08a406bf633715f6a6e9546295da3b02a41f0063
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="control-names-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사, 컨트롤 이름
컨트롤 클래스 및 속성 페이지 클래스, 형식 이름에 대 한 이름을 지정 하 고 컨트롤에 대 한 식별자를 입력 합니다. 제외 **약식 이름**, 다른 모든 필드 독립적으로 편집할 수 있습니다. 에 대 한 텍스트를 변경 하면 **약식 이름**,이 페이지의 다른 모든 필드의 이름에는 변경 내용이 반영 됩니다. 이 명명 문제는 모든 이름을 쉽게 식별할 수 있도록 사용자에 대 한 컨트롤을 개발할 때 설계 되었습니다.  
  
 **짧은 이름**  
 컨트롤에 대 한 약식된 이름을 제공 합니다. 기본적으로이 이름은에 제공 된 프로젝트 이름에 따라는 **새 프로젝트** 대화 상자. 제공한 이름은 해당 필드를 개별적으로 변경 하지 않는 한 클래스 이름, 형식 이름 및 유형 식별자를 결정 합니다.  
  
 **컨트롤 클래스 이름**  
 기본적으로 컨트롤 클래스의 이름 기반 약식 이름 뒤에 `C` 접두사로 및 `Ctrl` 접미사로 합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 컨트롤 클래스 이름이 `CPriceCtrl`합니다.  
  
 **제어.h 파일**  
 기본적으로 헤더 파일의 이름은 기반 약식 이름 뒤에 `Ctrl` 접미사로 및 `.h` 파일 확장명입니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 헤더 파일 이름이 `PriceCtrl.h`합니다. 이 필드의 이름은 컨트롤 클래스 이름과 일치 해야 합니다.  
  
 **제어.cpp 파일**  
 기본적으로 헤더 파일의 이름은 기반 약식 이름 뒤에 `Ctrl` 접미사로 및 `.cpp` 파일 확장명입니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 헤더 파일 이름이 `PriceCtrl.cpp`합니다. 이 필드의 이름은 헤더 이름이 일치 해야 합니다.  
  
 **컨트롤 형식 이름**  
 기본적으로 컨트롤 형식의 이름을 약식 이름 뒤에 따라 `Control`합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 컨트롤 클래스 형식 이름이 `Price Control`합니다. 이 필드에 값을 변경 하는 경우 이름에 상속 나타나는지 확인 합니다.  
  
 **컨트롤 종류 ID**  
 컨트롤 클래스의 컨트롤 형식 ID를 설정합니다. 컨트롤은 프로젝트에 추가 될 때 레지스트리에이 문자열을 씁니다. 컨테이너 응용 프로그램에서는 컨트롤의 인스턴스를 만들고이 문자열을 사용 합니다.  
  
 컨트롤 형식 ID에서 지정한 프로젝트 이름에 따라은 기본적으로는 **새 프로젝트** 대화 상자 및 짧은 이름입니다. 이 이름은 형식 이름이 일치 해야 합니다.  
  
 기본적으로 컨트롤 형식 ID는 다음과 같이 나타납니다.  
  
 *ProjectName.ShortName*Ctrl.1  
  
 이 대화 상자에서 짧은 이름을 변경 하면 컨트롤 형식 ID는 다음과 같이 나타납니다.  
  
 *ProjectName.NewShortName*Ctrl.1  
  
 **속성 페이지 클래스 이름**  
 기본적으로 속성 페이지 클래스의 이름은 기반 약식 이름 뒤에 `C` 접두사로 및 `PropPage` 접미사로 합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 속성 페이지 클래스 이름이 `CPricePropPage`합니다. 이 이름은 추가 된 컨트롤 클래스 이름에 일치 해야 `PropPage`합니다.  
  
 **속성 페이지.h 파일**  
 기본적으로 속성 페이지 헤더 파일의 이름 기반 약식 이름 뒤에로 `PropPage` 접미사로 및 `.h` 파일 확장명입니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 속성 페이지 헤더 파일 이름이 `PricePropPage.h`합니다. 이 이름은 클래스 이름과 일치 해야 합니다.  
  
 **속성 페이지.cpp 파일**  
 기본적으로 속성 페이지 구현 파일의 이름 기반 약식 이름 뒤에로 `PropPage` 접미사로 및 `.cpp` 파일 확장명입니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 속성 페이지 헤더 파일 이름이 `PricePropPage.cpp`합니다. 이 이름은 헤더 파일 이름과 일치 해야 합니다.  
  
 **속성 페이지 형식 이름**  
 기본적으로 속성 페이지 형식 이름은 다음 약식 이름 뒤에 따라 `Property Page`합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 속성 페이지 유형 이름이 `Price Property Page`합니다. 이 필드에 값을 변경 하는 경우 이름에 컨트롤 클래스 나타나는지 확인 합니다.  
  
 **속성 페이지 유형 ID**  
 속성 페이지 클래스의 ID를 설정 합니다. 컨트롤은 프로젝트에 적용 될 때 레지스트리에이 문자열을 씁니다. 컨테이너 응용 프로그램이이 문자열을 사용 하 여 컨트롤의 속성 페이지의 인스턴스를 만듭니다.  
  
 속성 페이지 형식 ID에서 지정한 프로젝트 이름에 따라은 기본적으로는 **새 프로젝트** 대화 상자 및 짧은 이름입니다. 이 이름은 형식 이름이 일치 해야 합니다.  
  
 기본적으로 속성 페이지 형식 ID는 다음과 같이 나타납니다.  
  
 *ProjectName.ShortName*PropPage.1  
  
 이 대화 상자에서 짧은 이름을 변경 하면 속성 페이지 형식 ID는 다음과 같이 나타납니다.  
  
 *ProjectName.NewShortName*PropPage.1  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)   
 [MFC ActiveX 컨트롤 마법사, 응용 프로그램 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [MFC ActiveX 컨트롤 마법사, 컨트롤 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)   
 [Visual C++ 프로젝트용 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)

