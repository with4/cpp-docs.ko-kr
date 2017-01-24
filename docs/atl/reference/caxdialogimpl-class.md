---
title: "CAxDialogImpl Class | Microsoft Docs"
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
  - "ATL::CAxDialogImpl"
  - "ATL.CAxDialogImpl"
  - "CAxDialogImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 대화 상자"
  - "CAxDialogImpl class"
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAxDialogImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 대화 상자 \(모달 또는 모덜리스\) ActiveX 컨트롤을 호스트 구현합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
class TBase= CWindow  
>  
class ATL_NO_VTABLE CAxDialogImpl :  
public CDialogImplBaseT< TBase>  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `CAxDialogImpl`.  
  
 *TBase*  
 기본 창 클래스에  **CDialogImplBaseT**.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAxDialogImpl::AdviseSinkMap](../Topic/CAxDialogImpl::AdviseSinkMap.md)|조언 또는 바이 싱크 맵에 이벤트 맵 개체의 모든 항목에이 메서드를 호출 합니다.|  
|[CAxDialogImpl::Create](../Topic/CAxDialogImpl::Create.md)|모덜리스 대화 상자를 만들려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::DestroyWindow](../Topic/CAxDialogImpl::DestroyWindow.md)|모덜리스 대화 상자를 제거 하려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::DoModal](../Topic/CAxDialogImpl::DoModal.md)|모달 대화 상자를 만들려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::EndDialog](../Topic/CAxDialogImpl::EndDialog.md)|모달 대화 상자를 제거 하려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::GetDialogProc](../Topic/CAxDialogImpl::GetDialogProc.md)|에 대 한 포인터를 가져오려면이 메서드를 호출 하는 `DialogProc` 콜백 함수입니다.|  
|[CAxDialogImpl::GetIDD](../Topic/CAxDialogImpl::GetIDD.md)|대화 상자 템플릿 리소스 ID를 가져오려면이 메서드를 호출 합니다.|  
|[CAxDialogImpl::IsDialogMessage](../Topic/CAxDialogImpl::IsDialogMessage.md)|이 대화 상자에 메시지를 사용할 것인지 확인 하려면이 메서드를 호출 하 고 있으면 메시지를 처리 합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAxDialogImpl::m\_bModal](../Topic/CAxDialogImpl::m_bModal.md)|디버그에만 존재 하는 변수를 빌드하고 모달 대화 상자의 경우 true로 설정 됩니다.|  
  
## 설명  
 `CAxDialogImpl`모달 또는 모덜리스 대화 상자를 만들 수 있습니다.  `CAxDialogImpl`기본 메시지 맵을 사용 하 여 적절 한 처리기 메시지 대화 상자 프로시저를 제공 합니다.  
  
 `CAxDialogImpl`파생 `CDialogImplBaseT`, 어떤 차례로 파생에서  *TBase* \(기본적으로 `CWindow`\)와 `CMessageMap`.  
  
 대화 상자 템플릿 리소스 ID를 지정 하는 IDD 멤버 클래스를 정의 합니다.  예를 들어, 사용 하 여 ATL 대화 상자 개체를 추가 된  **클래스 추가** 대화 상자 자동 추가 다음 줄에 클래스:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/CPP/caxdialogimpl-class_1.h)]  
  
 위치 `MyDialog` 되는  **약식 이름** ATL 대화 상자 마법사에서 입력 한.  
  
 참조  [대화 상자 구현](../../atl/implementing-a-dialog-box.md) 에 대 한 자세한 내용은.  
  
 모달 대화 상자에 있는 ActiveX 컨트롤을 사용 하 여 만든 노트 `CAxDialogImpl` 액셀러레이터 키를 지원 하지 않습니다.  액셀러레이터 키를 사용 하 여 만든 대화 상자에 지원 하려면 `CAxDialogImpl`, 모덜리스 대화 상자를 만들고 사용 하 여 자체 메시지 루프를 사용 하 여  [CAxDialogImpl::IsDialogMessage](../Topic/CAxDialogImpl::IsDialogMessage.md) 대기열에서 액셀러레이터 키를 처리 하는 메시지가 후.  
  
 에 대 한 자세한 내용은 `CAxDialogImpl`를 참조 하십시오  [ATL 컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md).  
  
## 상속 계층 구조  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [CDialogImpl Class](../../atl/reference/cdialogimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)