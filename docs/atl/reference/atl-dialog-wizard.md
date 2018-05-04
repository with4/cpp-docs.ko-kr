---
title: ATL 대화 상자 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e2d78f0a41edca44f8841d701cc87975c551466
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-dialog-wizard"></a>ATL 대화 상자 마법사
이 마법사에서 파생 된 ATL 대화 상자 개체를 프로젝트에 삽입 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)합니다. 대화 상자에서 파생 된 `CAxDialogImpl` ActiveX 컨트롤을 호스트할 수 있습니다.  
  
 기본값은 대화 상자 리소스를 만듭니다 **확인** 및 **취소** 단추입니다. 대화 상자 리소스를 편집 하 고 사용 하 여 ActiveX 컨트롤을 추가할 수는 [대화 상자 편집기](../../windows/dialog-editor.md) 리소스 뷰에서 합니다.  
  
 헤더 파일에 삽입 하는 마법사는 [메시지 맵을](../../atl/message-maps-atl.md) 기본 처리에 대 한 선언을 이벤트를 클릭 합니다. 참조 [대화 상자를 구현](../../atl/implementing-a-dialog-box.md) ATL 대화 상자에 대 한 자세한 내용은 합니다.  
  
 **짧은 이름**  
 ATL 대화 상자 개체에 대 한 약식된 이름을 설정합니다. 제공한 이름은 해당 필드를 개별적으로 변경 하지 않는 한 클래스 이름 및 파일 (.cpp 및.h) 이름이 결정 합니다.  
  
 `Class`  
 만들 클래스의 이름을 설정 합니다. 이 이름은에서 제공 하는 이름을 기반 **약식 이름**, 클래스 이름에 대 한 일반적인 접두사 'c' 앞에 옵니다.  
  
 **.h 파일**  
 새 개체의 클래스에 대 한 헤더 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 따라 **약식 이름**합니다. 사용자가 선택한 위치에 파일 이름을 저장 하거나 기존 파일을 클래스 선언을 추가 하려면 줄임표 단추를 클릭 합니다. 기존 파일을 선택 하면 마법사 파일이 저장 되지 것입니다 선택한 위치에 할 때까지 클릭 **마침** 마법사에서.  
  
 마법사는 파일을 덮어쓰지 않습니다. 선택한 경우 기존 파일의 이름을 클릭 하면 **마침**, 클래스 선언 파일의 내용을 추가 해야 할지 여부를 묻는 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.  
  
 **.cpp 파일**  
 새 개체의 클래스에 대 한 구현 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 따라 **약식 이름**합니다. 파일 이름을 원하는 위치에 저장 하려면 줄임표 단추를 클릭 합니다. 파일을 클릭할 때까지 선택한 위치에 저장 되지 않습니다 **마침** 마법사에서.  
  
 마법사는 파일을 덮어쓰지 않습니다. 경우 클릭할 때 기존 파일의 이름을 선택 **마침**, 마법사에서 클래스에 구현 파일의 내용에 추가할 것인지 여부를 묻는 메시지를 표시 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 대화 상자](../../atl/reference/adding-an-atl-dialog-box.md)

