---
title: "ATL 대화 상자 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.dlg.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 대화 상자 마법사"
  - "ATL 프로젝트, 대화 상자 리소스 추가"
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ATL 대화 상자 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 마법사에서는 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)에서 파생된 ATL 대화 상자 개체를 프로젝트에 삽입합니다.  `CAxDialogImpl`에서 파생된 대화 상자는 ActiveX 컨트롤을 호스팅할 수 있습니다.  
  
 이 마법사에서는 기본 **확인** 및 **취소** 단추가 있는 대화 상자 리소스를 만듭니다.  리소스 뷰에서 [대화 상자 편집기](../../mfc/dialog-editor.md)를 사용하여 대화 상자 리소스를 편집하고 ActiveX 컨트롤을 추가할 수 있습니다.  
  
 마법사에서는 기본 클릭 이벤트 처리를 위한 선언과 [메시지 맵](../../atl/message-maps-atl.md)을 헤더 파일에 삽입합니다.  ATL 대화 상자에 대한 자세한 내용은 [대화 상자 구현](../../atl/implementing-a-dialog-box.md)을 참조하십시오.  
  
 **약식 이름**  
 ATL 대화 상자 개체의 약식 이름을 설정합니다.  해당 필드를 개별적으로 변경하지 않는 한, 지정된 이름에 따라 클래스 이름과 파일\(.cpp 및 .h\) 이름이 결정됩니다.  
  
 `Class`  
 만들려는 클래스의 이름을 설정합니다.  이 이름은 **약식 이름**에 입력한 이름을 기본으로 하며, 클래스 이름의 일반적인 접두사인 'C'가 앞에 옵니다.  
  
 **.h 파일**  
 새 개체 클래스의 헤더 파일 이름을 설정합니다.  기본적으로 이 이름은 **약식 이름**에 입력한 이름을 기본으로 합니다.  원하는 위치에 파일 이름을 저장하거나 기존 파일에 클래스 선언을 추가하려면 줄임표\(...\) 단추를 클릭합니다.  기존 파일을 선택하면 마법사에서 **마침**을 클릭할 때까지 선택한 위치에 파일이 저장되지 않습니다.  
  
 또한 마법사에서는 파일을 덮어쓰지 않습니다.  기존 파일 이름을 선택한 경우 **마침**을 클릭하면 파일 내용에 클래스 선언을 추가할 것인지 묻는 메시지가 나타납니다.  파일을 추가하려면 **예**를 클릭하고, 마법사로 돌아가서 다른 파일 이름을 지정하려면 **아니요**를 클릭합니다.  
  
 **.cpp 파일**  
 새 개체 클래스의 구현 파일 이름을 설정합니다.  기본적으로 이 이름은 **약식 이름**에 입력한 이름을 기본으로 합니다.  원하는 위치에 파일 이름을 저장하려면 줄임표\(...\) 단추를 클릭합니다.  마법사에서 **마침**을 클릭할 때까지 선택한 위치에 파일이 저장되지 않습니다.  
  
 또한 마법사에서는 파일을 덮어쓰지 않습니다.  기존 파일 이름을 선택한 경우 **마침**을 클릭하면 파일 내용에 클래스 구현을 추가할 것인지 묻는 메시지가 나타납니다.  파일을 추가하려면 **예**를 클릭하고, 마법사로 돌아가서 다른 파일 이름을 지정하려면 **아니요**를 클릭합니다.  
  
## 참고 항목  
 [ATL Dialog Box](../../atl/reference/adding-an-atl-dialog-box.md)