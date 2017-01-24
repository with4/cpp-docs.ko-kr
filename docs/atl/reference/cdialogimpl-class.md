---
title: "CDialogImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialogImpl"
  - "ATL.CDialogImpl"
  - "ATL::CDialogImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogImpl class"
  - "대화 상자, ATL"
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
caps.latest.revision: 25
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDialogImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 모달 또는 모덜리스 대화 상자를 만드는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
class TBase= CWindow   
>  
class ATL_NO_VTABLE CDialogImpl :  
public CDialogImplBaseT< TBase>  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `CDialogImpl`.  
  
 *TBase*  
 새 클래스의 기본 클래스입니다.  기본 기본 클래스인  [CWindow](../../atl/reference/cwindow-class.md).  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[Create](../Topic/CDialogImpl::Create.md)|모덜리스 대화 상자를 만듭니다.|  
|[DestroyWindow](../Topic/CDialogImpl::DestroyWindow.md)|모덜리스 대화 상자를 소멸 시킵니다.|  
|[DoModal](../Topic/CDialogImpl::DoModal.md)|모달 대화 상자를 만듭니다.|  
|[EndDialog](../Topic/CDialogImpl::EndDialog.md)|모달 대화 상자를 소멸 시킵니다.|  
  
### CDialogImplBaseT 메서드  
  
|||  
|-|-|  
|[GetDialogProc](../Topic/CDialogImpl::GetDialogProc.md)|현재 대화 상자 프로시저를 반환합니다.|  
|[MapDialogRect](../Topic/CDialogImpl::MapDialogRect.md)|대화 상자 단위를 지정 된 사각형의 화면 단위를 \(픽셀\)에 매핑합니다.|  
|[OnFinalMessage](../Topic/CDialogImpl::OnFinalMessage.md)|일반적으로 마지막 메시지를 받은 후 호출 `WM_NCDESTROY`.|  
  
### 정적 함수  
  
|||  
|-|-|  
|[DialogProc](../Topic/CDialogImpl::DialogProc.md)|대화 상자에 전달 된 메시지를 처리 합니다.|  
|[StartDialogProc](../Topic/CDialogImpl::StartDialogProc.md)|대화 상자에 전달 된 메시지를 처리 하는 첫 번째 메시지를 받을 때 호출 됩니다.|  
  
## 설명  
 와 `CDialogImpl` 모달 또는 모덜리스 대화 상자를 만들 수 있습니다.  `CDialogImpl`기본 메시지 맵을 사용 하 여 적절 한 처리기 메시지 대화 상자 프로시저를 제공 합니다.  
  
 기본 클래스의 소멸자  **~ CWindowImplRoot** 확인 개체를 소멸 하기 전에 창이 사라집니다.  
  
 `CDialogImpl`파생 된  **CDialogImplBaseT**, 어떤 차례로 파생에서  **CWindowImplRoot**.  
  
> [!NOTE]
>  클래스를 정의  **IDD** 구성원 대화 상자 템플릿 리소스 ID를 지정 합니다.  예를 들어, ATL 프로젝트 마법사는 자동으로 다음 줄을 클래스에 추가:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/CPP/cdialogimpl-class_1.h)]  
  
 위치 `MyDlg` 되는  **약식 이름** 마법사에 입력 한  **이름** 페이지.  
  
|추가 정보|참조|  
|-----------|--------|  
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|  
|Atl에서 대화 상자 사용|[ATL 창 클래스](../../atl/atl-window-classes.md)|  
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|  
|대화 상자|[대화 상자](http://msdn.microsoft.com/library/windows/desktop/ms632588) 및 다음 항목에는[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)