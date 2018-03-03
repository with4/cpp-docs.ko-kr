---
title: "ATL Active Server Page 구성 요소 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.overview
dev_langs:
- C++
helpviewer_keywords:
- ASP components, creating in ATL
- ATL Active Server Page Component Wizard
ms.assetid: 5a5cb904-dbbf-44ea-ad3d-2ddd14c1d3c5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad2d707b5dbfc78ec8975471114bc87bf23fe5f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-active-server-page-component-wizard"></a>ATL Active Server Page 구성 요소 마법사
이 마법사는 프로젝트에는 ASP Active Server Pages () 구성 요소를 삽입합니다. Microsoft 인터넷 정보 서비스 (IIS)의 향상 된 웹 페이지 개발 아키텍처의 일부로 ASP 구성 요소를 사용합니다.  
  
 이 마법사를 사용 하 여 구성 요소의 스레딩 모델과 집계 지원을 지정할 수 있습니다. 오류 정보 인터페이스, 연결 지점 및 마샬링 자유 스레드 구성 요소에 대 한 지원을 나타낼 수도 있습니다.  
  
## <a name="remarks"></a>설명  
 Visual Studio 2008부터,이 마법사에서 생성 하는 등록 스크립트는 해당 COM 구성 요소 등록에서 **HKEY_CURRENT_USER** 대신 **HKEY_LOCAL_MACHINE**합니다. 이 동작을 수정 하려면 설정는 **모든 사용자에 대 한 구성 요소 등록** ATL 마법사의 옵션입니다.  
  
## <a name="names"></a>이름  
 개체, 인터페이스 및 프로젝트에 추가 하는 클래스에 대 한 이름을 지정 합니다. 제외 하 고 **약식 이름**, 다른 모든 상자의 개별적으로 편집할 수 있습니다. 에 대 한 텍스트를 변경 하면 **약식 이름**,이 페이지에 있는 다른 모든 상자의 이름에는 변경 내용이 반영 됩니다.  
  
 변경 하는 경우는 **Coclass** 에 변경 내용 COM 섹션에서 이름이 반영 됩니다는 **형식** 및 **ProgID** 상자 하지만 **인터페이스** 이름 변경 되지 않습니다. 이 명명 문제는 모든 이름을 쉽게 식별할 수 있도록 사용자에 대 한 컨트롤을 개발할 때 설계 되었습니다.  
  
### <a name="c"></a>C++  
 개체에 대해 만들어진 c + + 클래스에 대 한 정보를 제공 합니다.  
  
 **짧은 이름**  
 개체에 대 한 루트 이름을 설정합니다. 이름 확인을 제공 하는 `Class` 및 **Coclass** 이름는 **.cpp 파일** 및 **.h 파일** 이름는 **인터페이스**이름은 **형식** 이름 및 **ProgID**해당 필드를 개별적으로 변경 하지 않는 한 합니다.  
  
 **.h 파일**  
 새 개체의 클래스에 대 한 헤더 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 기본 **약식 이름**합니다. 사용자가 선택한 위치에 파일 이름을 저장 하거나 기존 파일을 클래스 선언을 추가 하려면 줄임표 단추를 클릭 합니다. 기존 파일을 선택 하면 마법사 파일이 저장 되지 것입니다 선택한 위치에 할 때까지 클릭 **마침** 마법사에서.  
  
 마법사는 파일을 덮어쓰지 않습니다. 선택한 경우 기존 파일의 이름을 클릭 하면 **마침**, 클래스 선언 파일의 내용을 추가 해야 할지 여부를 묻는 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.  
  
 **클래스**  
 만들 클래스의 이름을 설정 합니다. 이 이름은에서 제공 하는 이름을 기반 **약식 이름**, 클래스 이름에 대 한 일반적인 접두사 'c' 앞에 옵니다.  
  
 **.cpp 파일**  
 새 개체의 클래스에 대 한 구현 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 기본 **약식 이름**합니다. 파일 이름을 원하는 위치에 저장 하려면 줄임표 단추를 클릭 합니다. 파일을 클릭할 때까지 선택한 위치에 저장 되지 않습니다 **마침** 마법사에서.  
  
 마법사는 파일을 덮어쓰지 않습니다. 경우 클릭할 때 기존 파일의 이름을 선택 **마침**, 마법사에서 클래스에 구현 파일의 내용에 추가할 것인지 여부를 묻는 메시지를 표시 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.  
  
 **특성 사용**  
 개체가 특성을 사용 하는지 여부를 나타냅니다. 특성 사용된 ATL 프로젝트에 있는 개체를 추가 하는 경우에이 옵션이 선택 되며 변경할 수 없습니다. 즉, 특성이 지정 된 개체에 대해서만 특성 지원을 사용 하 여 만든 프로젝트에 추가할 수 있습니다.  
  
 특성을 지원 하지 않은 ATL 프로젝트에 대해이 옵션을 선택 하면 만들라는 특성 지원을 프로젝트에 추가할 것인지를 지정할 수 있습니다.  
  
 하지 않는 프로젝트는 기본적으로이 옵션을 설정한 후 추가 모든 개체 특성을 사용 하는 것으로 지정 됩니다 (확인란 선택). 특성을 사용 하지 않는 개체를 추가 하려면이 상자를 지울 수 있습니다.  
  
 참조 [ATL 프로젝트 마법사, 응용 프로그램 설정](../../atl/reference/application-settings-atl-project-wizard.md) 및 [특성의 기본 메커니즘](../../windows/basic-mechanics-of-attributes.md) 자세한 정보에 대 한 합니다.  
  
### <a name="com"></a>COM  
 개체에 대 한 COM 기능에 대 한 정보를 제공합니다.  
  
 **Coclass**  
 개체에서 지 원하는 인터페이스의 목록을 포함 하는 구성 요소 클래스의 이름을 설정 합니다. ATL 포함 되어 있지 않으므로이 옵션을 변경할 수 없습니다 프로젝트 또는이 개체에서 특성을 사용할 경우의 **coclass** 특성입니다.  
  
 **Type**  
 Coclass에 대 한 레지스트리에 나타나는 개체 설명을 설정 합니다.  
  
 **Interface**  
 개체에 대 한 작성 인터페이스를 설정 합니다. 이 인터페이스는 사용자 지정 메서드를 포함합니다.  
  
 **ProgID**  
 컨테이너 개체의 CLSID 대신 사용할 수 있는 이름을 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL Active Server Page 구성 요소](../../atl/reference/adding-an-atl-active-server-page-component.md)

