---
title: "ATL 대화 마법사 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 43540b1b86dbbf1777e7d5a7f6d8dec5dc618334
ms.lasthandoff: 02/24/2017

---
# <a name="atl-dialog-wizard"></a>ATL 대화 상자 마법사
이 마법사에서 파생 된 ATL 대화 상자 개체를 프로젝트에 삽입 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)합니다. 대화 상자에서 파생 된 `CAxDialogImpl` ActiveX 컨트롤을 호스팅할 수 있습니다.  
  
 기본값은 대화 상자 리소스를 만듭니다 **확인** 및 **취소** 단추입니다. 대화 상자 리소스를 편집 하 고 사용 하 여 ActiveX 컨트롤을 추가할 수는 [대화 상자 편집기](../../windows/dialog-editor.md) 리소스 보기에서.  
  
 헤더 파일에 삽입 하는 마법사는 [메시지 맵을](../../atl/message-maps-atl.md) 기본 처리를 위한 선언과 이벤트를 클릭 합니다. 참조 [대화 상자 구현](../../atl/implementing-a-dialog-box.md) ATL 대화 상자에 대 한 자세한 내용은 합니다.  
  
 **짧은 이름**  
 ATL 대화 상자 개체에 대 한 약식된 이름을 설정합니다. 제공 하는 이름은 해당 필드를 개별적으로 변경 하지 않는 한 클래스 이름 및 파일 (.cpp 및.h) 이름이 결정 합니다.  
  
 `Class`  
 만들 클래스의 이름을 설정 합니다. 이 이름은 기반에서 제공한 이름으로 **약식 이름**, 클래스 이름에 대 한 일반적인 접두사 'c' 앞에 옵니다.  
  
 **.h 파일**  
 새 개체의 클래스에 대 한 헤더 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 따라 **약식 이름**합니다. 사용자가 선택한 위치에 파일 이름을 저장 하거나 기존 파일을 클래스 선언 추가 하려면 줄임표 단추를 클릭 합니다. 기존 파일을 선택 하면 마법사 파일이 저장 되지 것입니다 선택한 위치에 때까지 클릭 **마침** 마법사에서.  
  
 마법사 파일을 덮어쓰지 않습니다. 선택한 경우 기존 파일의 이름을 클릭 하면 **마침**, 클래스 선언에는 파일의 내용을 추가할 것인지 묻는 합니다. 클릭 **예** ; 파일을 추가 클릭 **No** 마법사 돌아가서 다른 파일 이름을 지정 하려면.  
  
 **.cpp 파일**  
 새 개체의 클래스에 대 한 구현 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 따라 **약식 이름**합니다. 원하는 위치에 파일 이름을 저장 하려면 줄임표 단추를 클릭 합니다. 클릭할 때까지 파일이 선택한 위치에 저장 되지는 않습니다 **마침** 마법사에서.  
  
 마법사 파일을 덮어쓰지 않습니다. 선택한 경우 기존 파일의 이름을 클릭 하면 **완료**, 마법사에서 클래스에 구현 파일의 내용에 추가할 것인지 여부를 묻는 메시지를 표시 합니다. 클릭 **예** ; 파일을 추가 클릭 **No** 마법사 돌아가서 다른 파일 이름을 지정 하려면.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 대화 상자](../../atl/reference/adding-an-atl-dialog-box.md)


