---
title: "ATL 컨트롤 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
- ATL Control Wizard
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a9167153c2b827e1bc2597e830e9b3c82ee31b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-control-wizard"></a>ATL 컨트롤 마법사
ATL 프로젝트 (또는 MFC 프로젝트에 ATL 지원)에 대 한 삽입 ATL 컨트롤입니다. 세 가지 종류의 컨트롤 중 하나를 삽입 하려면이 마법사를 사용할 수 있습니다.  
  
-   표준 컨트롤  
  
-   복합 컨트롤  
  
-   DHTML 컨트롤  
  
 또한 지정할 수 있습니다 최소 컨트롤을 제거 하는 인터페이스에서는 [인터페이스](../../atl/reference/interfaces-atl-control-wizard.md) 목록으로에서 대부분의 컨테이너에서 컨트롤 열기에 대 한 기본값으로 제공 됩니다. 컨트롤에 대 한 지원 되는 원하는 인터페이스를 설정할 수는 **인터페이스** 마법사의 페이지입니다.  
  
## <a name="remarks"></a>설명  
 이 마법사에서 생성 하는 등록 스크립트 HKEY_LOCAL_MACHINE 대신 HKEY_CURRENT_USER에 COM 구성 요소를 등록 합니다. 이 동작을 수정 하려면 설정는 **모든 사용자에 대 한 구성 요소 등록** ATL 마법사의 옵션입니다.  
  
## <a name="names"></a>이름  
 개체, 인터페이스 및 프로젝트에 추가 하는 클래스에 대 한 이름을 지정 합니다. 제외 하 고 **약식 이름**, 다른 모든 상자의 독립적으로 변경할 수 있습니다. 에 대 한 텍스트를 변경 하면 **약식 이름**,이 페이지에 있는 다른 모든 상자의 이름에는 변경 내용이 반영 됩니다. 변경 하는 경우는 **Coclass** 에 변경 내용 COM 섹션에서 이름이 반영 됩니다는 **형식** 상자 하지만 **인터페이스** 이름 및 **ProgID** 수행 변경 되지 않습니다. 이 명명 문제는 모든 이름을 쉽게 식별할 수 있도록 사용자에 대 한 컨트롤을 개발할 때 설계 되었습니다.  
  
> [!NOTE]
>  **Coclass** 은 하지 않는 컨트롤에만 편집할 수 있습니다. 프로젝트에서 특성을 사용 하는 경우 편집할 수 없습니다 **Coclass**합니다.  
  
### <a name="c"></a>C++  
 개체를 구현 하기 위해 만든 c + + 클래스에 대 한 정보를 제공 합니다.  
  
 **짧은 이름**  
 개체에 대 한 약식된 이름을 설정합니다. 클래스를 결정 하는 사용자가 제공한 이름 및 **Coclass** 이름, 파일 (합니다. CPP 및 합니다. H) 이름에서 인터페이스 이름 및 **형식** 이름, 해당 필드를 개별적으로 변경 하지 않는 한 합니다.  
  
 **클래스**  
 개체를 구현 하는 클래스의 이름을 설정 합니다. 이 이름은에서 제공 하는 이름을 기반 **약식 이름**, 클래스 이름에 대 한 일반적인 접두사 'c' 앞에 옵니다.  
  
 **.h 파일**  
 새 개체의 클래스에 대 한 헤더 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 기본 **약식 이름**합니다. 사용자가 선택한 위치에 파일 이름을 저장 하거나 기존 파일을 클래스 선언을 추가 하려면 줄임표 단추를 클릭 합니다. 기존 파일을 선택 하면 마법사 파일이 저장 되지 것입니다 선택한 위치에 할 때까지 클릭 **마침**합니다.  
  
 마법사는 파일을 덮어쓰지 않습니다. 선택한 경우 기존 파일의 이름을 클릭 하면 **마침**, 클래스 선언 파일의 내용을 추가 해야 할지 여부를 묻는 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.  
  
 **.cpp 파일**  
 새 개체의 클래스에 대 한 구현 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 기본 **약식 이름**합니다. 파일 이름을 원하는 위치에 저장 하려면 줄임표 단추를 클릭 합니다. 파일을 클릭할 때까지 선택한 위치에 저장 되지 않습니다 **마침** 마법사에서.  
  
 마법사는 파일을 덮어쓰지 않습니다. 경우 클릭할 때 기존 파일의 이름을 선택 **마침**, 마법사에서 클래스에 구현 파일의 내용에 추가할 것인지 여부를 묻는 메시지를 표시 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.  
  
 **특성 사용**  
 개체가 특성을 사용 하는지 여부를 나타냅니다. 특성 사용된 ATL 프로젝트에 있는 개체를 추가 하는 경우에이 옵션이 선택 되며 변경할 수 없습니다. 즉, 특성이 지정 된 개체에 대해서만 특성 지원을 사용 하 여 만든 프로젝트에 추가할 수 있습니다.  
  
 특성이 지정 된 개체 특성을 사용 하는 ATL 프로젝트에만 추가할 수 있습니다. 특성을 지원 하지 않은 ATL 프로젝트에 대해이 옵션을 선택 하면 만들라는 특성 지원을 프로젝트에 추가할 것인지를 지정할 수 있습니다.  
  
 기본적으로이 옵션을 설정한 후 추가 모든 개체 특성을 사용 하는 것으로 지정 됩니다 (확인란 선택). 특성을 사용 하지 않는 개체를 추가 하려면이 상자를 지울 수 있습니다.  
  
 참조 [ATL 프로젝트 마법사, 응용 프로그램 설정](../../atl/reference/application-settings-atl-project-wizard.md) 및 [특성의 기본 메커니즘](../../windows/basic-mechanics-of-attributes.md) 자세한 정보에 대 한 합니다.  
  
### <a name="com"></a>COM  
 개체에 대 한 COM 기능에 대 한 정보를 제공합니다.  
  
 **Coclass**  
 개체에서 지 원하는 인터페이스의 목록을 포함 하는 구성 요소 클래스의 이름을 설정 합니다.  
  
> [!NOTE]
>  특성을 사용 하 여 프로젝트를 만들면 또는 ATL 포함 되어 있지 않으므로이 옵션을 변경할 수 없습니다을 지정할 경우이 마법사 페이지에서 컨트롤 특성을 사용 하는 경우는 **coclass** 특성입니다.  
  
 **Interface**  
 개체에 대 한 인터페이스의 이름을 설정합니다. 기본적으로 인터페이스 이름이 "I"로 시작 됩니다.  
  
 **Type**  
 설정 하는 레지스트리에 나타나는 개체 설명  
  
 **ProgID**  
 컨테이너 개체의 CLSID 대신 사용할 수 있는 이름을 설정 합니다. 이 필드가 자동으로 채워지지 않습니다. 이 필드를 수동으로 채우지 마십시오 컨트롤 다른 도구를 하지 못할 수 있습니다. 예를 들어 없이 생성 되는 ActiveX 컨트롤을 `ProgID` 에서 사용할 수 없는 **ActiveX 컨트롤 삽입** 대화 상자. 대화 상자에 대 한 자세한 내용은 참조 [ActiveX 컨트롤 삽입 대화 상자](../../windows/insert-activex-control-dialog-box.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 컨트롤](../../atl/reference/adding-an-atl-control.md)   
 [복합 컨트롤에 기능 추가](../../atl/adding-functionality-to-the-composite-control.md)   
 [ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)

