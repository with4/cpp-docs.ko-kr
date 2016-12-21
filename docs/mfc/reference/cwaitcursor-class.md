---
title: "CWaitCursor Class | Microsoft Docs"
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
  - "CWaitCursor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "커서, wait cursor"
  - "CWaitCursor class"
  - "wait cursors"
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWaitCursor Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

긴 작업을 하 고 있는 동안 보통 모래시계 모양으로 표시 되는 대기 커서를 표시 한 줄 수가 있습니다.  
  
## 구문  
  
```  
class CWaitCursor  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWaitCursor::CWaitCursor](../Topic/CWaitCursor::CWaitCursor.md)|생성 한 `CWaitCursor` 개체와 대기 커서를 표시 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWaitCursor::Restore](../Topic/CWaitCursor::Restore.md)|변경 된 후에 대기 커서를 복원 합니다.|  
  
## 설명  
 `CWaitCursor`기본 클래스에 없는 것입니다.  
  
 좋은 Windows 프로그래밍 상당한 시간이 걸리는 작업을 수행 하는 때마다 대기 커서를 표시 해야 합니다.  
  
 대기 커서를 표시 하려면 단순히 정의 `CWaitCursor` 변수 전에 시간이 오래 걸리는 작업을 수행 하는 코드입니다.  개체의 생성자는 자동으로 대기 커서가 표시 됩니다.  
  
 개체가 범위를 벗어날 때 \(블록의 끝에는 `CWaitCursor` 개체 선언\), 소멸자가 이전 커서에 커서를 설정 합니다.  즉, 개체는 자동으로 필요한 정리를 수행합니다.  
  
> [!NOTE]
>  생성자 및 소멸자의 작동 방법, 때문에 `CWaitCursor` 개체는 항상 로컬 변수로 선언\-전역 변수를 선언 하지는 않으며 할당 된  **새**.  
  
 변경, 메시지 상자 또는 대화 상자에서 호출 표시 등 커서 발생할 작업을 수행 하는 경우는  [복원](../Topic/CWaitCursor::Restore.md) 멤버 함수 대기 커서를 복원 합니다.  호출할 수 있는  **복원** 도 때 대기 커서가 현재 표시 됩니다.  
  
 대기 커서를 표시 하는 다른 방법은의 조합을 사용 하는  [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md),  [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md), 및  [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md).  그러나 `CWaitCursor` 긴 작업을 마치면 커서 이전 커서를 설정 하지 않아도 되므로 사용 하기가 쉽습니다.  
  
> [!NOTE]
>  MFC 설정 하 고 복원 하는 커서를 사용 하는  [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md) 가상 함수입니다.  사용자 지정 동작을 제공 하려면이 함수를 재정의할 수 있습니다.  
  
## 상속 계층 구조  
 `CWaitCursor`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 예제  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/CPP/cwaitcursor-class_1.cpp)]  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)   
 [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)   
 [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md)   
 [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)   
 [I: 방법 변경 클래스 Mfc 응용 프로그램에서 마우스 커서?](http://go.microsoft.com/fwlink/?LinkID=128044)