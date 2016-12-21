---
title: "ICommandSource Interface | Microsoft Docs"
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
  - "ICommandSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandSource interface"
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: 24
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandSource Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령 소스 개체에서 사용자 정의 컨트롤에 전달 된 명령 관리 합니다.  
  
## 구문  
  
```  
interface class ICommandSource  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ICommandSource::AddCommandHandler](../Topic/ICommandSource::AddCommandHandler.md)|명령 소스 개체에 명령 처리기를 추가합니다.|  
|[ICommandSource::AddCommandRangeHandler](../Topic/ICommandSource::AddCommandRangeHandler.md)|명령 소스 개체에 그룹의 명령 처리기를 추가합니다.|  
|[ICommandSource::AddCommandRangeUIHandler](../Topic/ICommandSource::AddCommandRangeUIHandler.md)|그룹의 사용자 인터페이스 명령 메시지 처리기 명령 소스 개체에 추가합니다.|  
|[ICommandSource::AddCommandUIHandler](../Topic/ICommandSource::AddCommandUIHandler.md)|명령 소스 개체에는 사용자 인터페이스 명령 메시지 처리기를 추가합니다.|  
|[ICommandSource::PostCommand](../Topic/ICommandSource::PostCommand.md)|처리 될 때까지 기다리지 않고 메시지를 게시 합니다.|  
|[ICommandSource::RemoveCommandHandler](../Topic/ICommandSource::RemoveCommandHandler.md)|명령 소스 개체에서 명령 처리기를 제거합니다.|  
|[ICommandSource::RemoveCommandRangeHandler](../Topic/ICommandSource::RemoveCommandRangeHandler.md)|그룹 명령 처리기의 명령 소스 개체에서 제거합니다.|  
|[ICommandSource::RemoveCommandRangeUIHandler](../Topic/ICommandSource::RemoveCommandRangeUIHandler.md)|명령 소스 개체에서 그룹의 사용자 인터페이스 명령 메시지 처리기를 제거합니다.|  
|[ICommandSource::RemoveCommandUIHandler](../Topic/ICommandSource::RemoveCommandUIHandler.md)|메시지 처리기는 사용자 인터페이스 명령 명령 소스 개체에서 제거합니다.|  
|[ICommandSource::SendCommand](../Topic/ICommandSource::SendCommand.md)|메시지를 전송 하 고 반환 하기 전에 처리할 수 있도록 기다립니다.|  
  
## 설명  
 MFC 보기에서 사용자 정의 컨트롤을 호스팅할 때 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) 경로 명령과 업데이트 명령 UI 메시지를 사용자 정의 컨트롤 MFC 명령 \(예: 프레임 메뉴 항목 및 도구 모음 단추\)을 처리할 수 있도록 합니다.  구현 하 여 [ICommandTarget Interface](../../mfc/reference/icommandtarget-interface.md), 사용자 정의 컨트롤에 대 한 참조를 제공 된 `ICommandSource` 개체.  
  
 `ICommandTarget` 사용 방법 예제는 [방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)를 참조하십시오.  
  
 Windows Forms을 사용 하 여에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## 요구 사항  
 **헤더:** afxwinforms.h \(어셈블리 atlmfc\\lib\\mfcmifc80.dll에서 정의\)  
  
## 참고 항목  
 [방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget Interface](../../mfc/reference/icommandtarget-interface.md)