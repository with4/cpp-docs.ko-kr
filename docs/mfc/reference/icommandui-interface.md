---
title: "ICommandUI Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ICommandUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandUI interface"
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandUI Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 인터페이스 명령을 관리합니다.  
  
## 구문  
  
```  
interface class ICommandUI  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ICommandUI::Check](../Topic/ICommandUI::Check.md)|이 명령에 대 한 사용자 인터페이스 항목에 적절 한 선택 상태를 설정합니다.|  
|[ICommandUI::ContinueRouting](../Topic/ICommandUI::ContinueRouting.md)|계속 다운 처리기 체인이 현재 메시지 라우팅 명령 라우팅 메커니즘을 설명 합니다.|  
|[ICommandUI::Enabled](../Topic/ICommandUI::Enabled.md)|이 명령에 대 한 사용자 인터페이스 항목을 사용할 수 있거나.|  
|[ICommandUI::ID](../Topic/ICommandUI::ID.md)|표시 되는 사용자 인터페이스 개체의 ID를 가져옵니다는 `ICommandUI` 개체입니다.|  
|[ICommandUI::Index](../Topic/ICommandUI::Index.md)|표시 되는 사용자 인터페이스 개체의 인덱스를 가져옵니다는 `ICommandUI` 개체입니다.|  
|[ICommandUI::Radio](../Topic/ICommandUI::Radio.md)|이 명령에 대 한 사용자 인터페이스 항목에 적절 한 선택 상태를 설정합니다.|  
|[ICommandUI::Text](../Topic/ICommandUI::Text.md)|이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정합니다.|  
  
## 설명  
 이 인터페이스 메서드 및 사용자 인터페이스 명령을 관리 하는 속성을 제공 합니다.  `ICommandUI`유사한 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)을 제외 하 고, `ICommandUI` .NET 구성 요소와 상호 작용 하는 MFC 응용 프로그램에 사용 됩니다.  
  
 `ICommandUI`내에서 사용 되는 `ON_UPDATE_COMMAND_UI` 처리기에는  [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)\-클래스를 파생 합니다.  사용자의 응용 프로그램 선택을 클릭 하면 각 메뉴 항목은 메뉴 사용으로 표시 됩니다 또는 사용 하지 않도록 설정 합니다.  대상의 각 메뉴 명령 구현 하 여이 정보를 제공 된 `ON_UPDATE_COMMAND_UI` 처리기.  각 명령 사용자 인터페이스 개체를 응용 프로그램에서에 대 한 메시지 맵 엔트리 및 각 처리기에 대 한 함수 프로토타입을 만들려면 속성 창을 사용 합니다.  
  
 하는 방법에 대 한 자세한 내용은 `ICommandUI` 인터페이스 명령 라우팅에 사용을 참조 하십시오 [방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Windows Forms을 사용 하 여에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 사용자 인터페이스 명령을 MFC에서 관리 하는 방법에 대 한 자세한 내용은 [CCmdUI Class](../../mfc/reference/ccmdui-class.md).  
  
## 요구 사항  
 **헤더:** afxwinforms.h \(어셈블리 atlmfc\\lib\\mfcmifc80.dll에서 정의\)  
  
## 참고 항목  
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)