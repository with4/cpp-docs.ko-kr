---
title: "ATL 속성 페이지 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.ppg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding property pages
- ATL Property Page Wizard
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f97b4fcc84f9099ca7017eabd7ae5ead62cfe63
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-property-page-wizard"></a>ATL 속성 페이지 마법사
이 마법사 [ATL 프로젝트에 속성 페이지를 추가](../../atl/reference/adding-an-atl-property-page.md) 또는 MFC 프로젝트에 ATL 지원 합니다. 속성을 설정 하기 위한 사용자 인터페이스를 제공 하는 ATL 속성 페이지 (또는 메서드를 호출할) 하나 이상의 COM 개체입니다.  
  
## <a name="remarks"></a>설명  
 Visual Studio 2008부터,이 마법사에서 생성 하는 등록 스크립트는 해당 COM 구성 요소 등록에서 **HKEY_CURRENT_USER** 대신 **HKEY_LOCAL_MACHINE**합니다. 이 동작을 수정 하려면 설정는 **모든 사용자에 대 한 구성 요소 등록** ATL 마법사의 옵션입니다.  
  
## <a name="names"></a>이름  
 개체, 인터페이스 및 프로젝트에 추가 하는 클래스에 대 한 이름을 지정 합니다. 제외 하 고 **약식 이름**, 다른 모든 상자의 독립적으로 편집할 수 있습니다. 에 대 한 텍스트를 변경 하면 **약식 이름**,이 페이지에 있는 다른 모든 상자의 이름에는 변경 내용이 반영 됩니다. 변경 하는 경우는 **Coclass** 에 변경 내용 COM 섹션에서 이름이 반영 됩니다는 **형식** 및 **ProgID** 상자입니다. 이 명명 문제는 모든 이름을 쉽게 식별할 수 있도록 사용자에 대 한 속성 페이지를 개발 하는 경우 설계 되었습니다.  
  
> [!NOTE]
>  **Coclass** 하지 않는 프로젝트 에서만 편집할 수 있습니다. 프로젝트에서 특성을 사용 하는 경우 편집할 수 없습니다 **Coclass**합니다.  
  
### <a name="c"></a>C++  
 개체를 구현 하기 위해 만든 c + + 클래스에 대 한 정보를 제공 합니다.  
  
|||  
|-|-|  
|용어|정의|  
|**짧은 이름**|개체에 대 한 약식된 이름을 설정합니다. 클래스를 결정 하는 사용자가 제공한 이름 및 **Coclass** 이름, 파일 (**.cpp** 및 **.h**) 이름는 **형식** 이름과  **ProgID**해당 필드를 개별적으로 변경 하지 않는 한 합니다.|  
|**.h 파일**|새 개체의 클래스에 대 한 헤더 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 기본 **약식 이름**합니다. 사용자가 선택한 위치에 파일 이름을 저장 하거나 기존 파일을 클래스 선언을 추가 하려면 줄임표 단추를 클릭 합니다. 기존 파일을 선택 하면 마법사 파일이 저장 되지 것입니다 선택한 위치에 할 때까지 클릭 **마침** 마법사에서.<br /><br /> 마법사는 파일을 덮어쓰지 않습니다. 선택한 경우 기존 파일의 이름을 클릭 하면 **마침**, 클래스 선언 파일의 내용을 추가 해야 할지 여부를 묻는 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.|  
|**클래스**|개체를 구현 하는 클래스의 이름을 설정 합니다. 이 이름은에서 제공 하는 이름을 기반 **약식 이름**, 클래스 이름에 대 한 일반적인 접두사 'c' 앞에 옵니다.|  
|**.cpp 파일**|새 개체의 클래스에 대 한 구현 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 기본 **약식 이름**합니다. 파일 이름을 원하는 위치에 저장 하려면 줄임표 단추를 클릭 합니다. 파일을 클릭할 때까지 선택한 위치에 저장 되지 않습니다 **마침** 마법사에서.<br /><br /> 마법사는 파일을 덮어쓰지 않습니다. 경우 클릭할 때 기존 파일의 이름을 선택 **마침**, 마법사에서 클래스에 구현 파일의 내용에 추가할 것인지 여부를 묻는 메시지를 표시 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.|  
|**특성 사용**|개체가 특성을 사용 하는지 여부를 나타냅니다. 특성 사용된 ATL 프로젝트에 있는 개체를 추가 하는이 옵션을 선택 하 고 변경할 수 없습니다, 즉, 추가할 수 있습니다만 인 한 개체 특성 지원을 사용 하 여 만든 프로젝트에 있습니다.<br /><br /> 특성이 지정 된 개체 특성을 사용 하는 ATL 프로젝트에만 추가할 수 있습니다. 특성을 지원 하지 않은 ATL 프로젝트에 대해이 옵션을 선택 하면 만들라는 특성 지원을 프로젝트에 추가할 것인지를 지정할 수 있습니다.<br /><br /> 기본적으로이 옵션을 설정한 후 추가 모든 개체 특성을 사용 하는 것으로 지정 됩니다 (확인란 선택). 특성을 사용 하지 않는 개체를 추가 하려면이 상자를 지울 수 있습니다.<br /><br /> 참조 [ATL 프로젝트 마법사, 응용 프로그램 설정](../../atl/reference/application-settings-atl-project-wizard.md) 및 [특성의 기본 메커니즘](../../windows/basic-mechanics-of-attributes.md) 자세한 정보에 대 한 합니다.|  
  
### <a name="com"></a>COM  
 개체에 대 한 COM 기능에 대 한 정보를 제공합니다.  
  
 **Coclass**  
 개체에서 지 원하는 인터페이스의 목록을 포함 하는 구성 요소 클래스의 이름을 설정 합니다.  
  
> [!NOTE]
>  특성을 사용 하 여 프로젝트를 만들면 또는 ATL 포함 되어 있지 않으므로이 옵션을 변경할 수 없습니다을 지정할 경우이 마법사 페이지에서 속성 페이지 특성을 사용 하는 경우는 `coclass` 특성입니다.  
  
 **Type**  
 설정 하는 레지스트리에 나타나는 개체 설명  
  
 **ProgID**  
 컨테이너 개체의 CLSID 대신 사용할 수 있는 이름을 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [옵션, ATL 속성 페이지 마법사](../../atl/reference/options-atl-property-page-wizard.md)   
 [문자열, ATL 속성 페이지 마법사](../../atl/reference/strings-atl-property-page-wizard.md)   
 [예: 속성 페이지 구현](../../atl/example-implementing-a-property-page.md)

