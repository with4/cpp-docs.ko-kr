---
title: "MFC ActiveX 컨트롤 마법사, 컨트롤 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.settings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX 컨트롤 마법사, 컨트롤 설정"
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# MFC ActiveX 컨트롤 마법사, 컨트롤 설정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 마법사 페이지를 사용하여 컨트롤을 동작시킬 방법을 지정합니다.  예를 들어, 표준 Windows 컨트롤 형식의 컨트롤을 기준으로 하거나 그 동작과 모양을 최적화하거나 컨트롤이 다른 컨트롤의 컨테이너 역할을 할 수 있음을 지정할 수 있습니다.  
  
 이 페이지의 옵션을 선택하여 컨트롤의 효율성을 최대화하는 방법에 대한 자세한 내용은 [MFC ActiveX 컨트롤: 최적화](../../mfc/mfc-activex-controls-optimization.md)을 참조하십시오.  
  
## UI 요소 목록  
 **컨트롤 기준**  
 이 목록에서 컨트롤을 상속해야 하는 일종의 컨트롤을 선택할 수 있습니다.  목록은 commctrl.h에 지정되어 있는 추가 공용 컨트롤과 `CreateWindowEx`에 사용할 수 있는 컨트롤 클래스의 하위 집합입니다.  Your selection determines the style of the control in the `PreCreateWindow` function in the *ProjName*Ctrl.cpp file.  자세한 내용은 [MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md)을 참조하십시오.  
  
|컨트롤|설명|  
|---------|--------|  
|**BUTTON**|Windows 단추 컨트롤|  
|**COMBOBOX**|Windows 콤보 상자 컨트롤|  
|**EDIT**|Windows 편집 상자 컨트롤|  
|**LISTBOX**|Windows 목록 상자 컨트롤|  
|**SCROLLBAR**|Windows 스크롤 막대 컨트롤|  
|**STATIC**|Windows 정적 컨트롤|  
|**msctls\_hotkey32**|핫 키 공용 컨트롤|  
|**msctls\_progress32**|진행률 표시줄 공용 컨트롤|  
|**msctls\_statusbar32**|상태 표시줄 공용 컨트롤|  
|**msctls\_trackbar32**|트랙 표시줄 공용 컨트롤|  
|**msctls\_updown32**|스핀 단추\(또는 up\-down\) 공용 컨트롤|  
|**SysAnimate32**|애니메이션 공용 컨트롤|  
|**SysHeader32**|헤더 공용 컨트롤|  
|**SysListView32**|목록 뷰 공용 컨트롤|  
|**SysTabControl32**|탭 공용 컨트롤|  
|**SysTreeView32**|트리 뷰 공용 컨트롤|  
  
 **표시되었을 때 활성화**  
 컨트롤에 액세스할 때 해당 컨트롤에 대한 창을 생성하도록 지정합니다.  기본적으로 **표시되었을 때 활성화** 옵션이 선택되어 있습니다.  컨테이너에서 필요로 할 때\(사용자가 마우스를 클릭할 때\)까지 컨트롤 활성화를 지연하려면 이 옵션의 선택을 취소합니다.  이 기능을 해제하면 기능을 다시 사용할 때까지 창을 만드는 비용이 들지 않습니다.  자세한 내용은 [표시되었을 때 활성화 옵션 해제](../../mfc/turning-off-the-activate-when-visible-option.md)을 참조하십시오.  
  
 **런타임에 숨김**  
 런타임에 컨트롤에 사용자 인터페이스가 없도록 지정합니다.  타이머가 사용자에게 표시되지 않도록 설정할 수 있는 일종의 컨트롤입니다.  
  
 **\[정보\] 대화 상자 포함**  
 컨트롤이 버전 번호와 저작권 정보를 표시하는 표준 Windows **정보** 대화 상자를 갖도록 지정합니다.  
  
> [!NOTE]
>  사용자가 컨트롤의 도움말에 액세스하는 방법은 도움말을 구현한 방법과 컨트롤 도움말을 컨테이너 도움말과 통합했는지 여부에 따라 다릅니다.  For more information about how to integrate help, on the [MSDN Library](http://go.microsoft.com/fwlink/?linkID=150542) website, search for "Adding Context\-Sensitive Help to an MFC ActiveX Control".  
  
 When you select this option, it inserts the `AboutBox` control method in the project control class \(C*ProjName*Ctrl.cpp\) and adds AboutBox to the project dispatch map.  기본적으로 이 옵션이 선택됩니다.  
  
 **그리기 코드 최적화**  
 동일한 장치 컨텍스트로 그려지는 컨테이너 컨트롤이 모두 그려진 후에 자동으로 컨테이너가 원본 GDI 개체를 복원하도록 지정합니다.  이 기능에 대한 자세한 내용은 [컨트롤 그리기 최적화](../../mfc/optimizing-control-drawing.md)를 참조하십시오.  
  
 **창 없는 활성화**  
 컨트롤이 활성화될 때 창을 생성하지 않도록 지정합니다.  창 없는 활성화 기능으로 직사각형 또는 투명한 컨트롤이 가능하며 창 없는 컨트롤은 창을 필요로 하는 컨트롤보다 시스템 오버헤드를 더 줄일 수 있습니다.  창 없는 활성화는 잘리지 않는 장치 컨텍스트나 깜빡임 없는 활성화를 허용하지 않습니다.  1996년 전에 만들어진 컨테이너는 창 없는 활성화를 지원하지 않습니다.  이 옵션을 사용하는 방법에 대한 자세한 내용은 [창 없는 활성화 제공](../../mfc/providing-windowless-activation.md)을 참조하십시오.  
  
 **잘리지 않는 장치 컨텍스트**  
 Overrides [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) in the control header \(*projname*ctrl.h\) to disable the call to `IntersectClipRect` made by `COleControl`.  이 옵션을 선택하는 경우 속도 면에서 약간의 이점을 제공합니다.  **창 없는 활성화** 옵션을 선택한 경우에는 이 기능을 사용할 수 없습니다.  자세한 내용은 [잘리지 않는 장치 컨텍스트 사용](../../mfc/using-an-unclipped-device-context.md)을 참조하십시오.  
  
 **깜빡임 없는 활성화**  
 컨트롤의 활성 및 비활성 상태 사이에 발생하는 그리기 작업과 여기에 동반되는 시각적 깜박임을 제거합니다.  **창 없는 활성화** 옵션을 선택한 경우에는 이 기능을 사용할 수 없습니다.  이 옵션을 설정하면 `noFlickerActivate` 플래그는 [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)에서 반환되는 플래그 중 하나입니다.  자세한 내용은 [깜빡임 없는 활성화 제공](../../mfc/providing-flicker-free-activation.md)을 참조하십시오.  
  
 **\[개체 삽입\] 대화 상자에서 사용 가능**  
 활성화된 컨테이너에 대해 **개체 삽입** 대화 상자에서 컨트롤을 사용할 수 있도록 지정합니다.  이 옵션을 선택하는 경우 `afxRegInsertable` 플래그는 `AfxOleRegisterControlClass`에서 반환하는 플래그 중 하나입니다.  **개체 삽입** 대화 상자를 사용하여 새로 만든 개체나 기존 개체를 복합 문서에 삽입할 수 있습니다.  
  
 **비활성화 상태일 때 마우스 포인터 알림**  
 컨트롤이 활성인지 여부에 관계 없이 마우스 포인터 알림을 처리하도록 컨트롤을 활성화합니다.  이 옵션을 선택하는 경우 `pointerInactive` 플래그는 [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)에서 반환하는 플래그 중 하나입니다.  이 옵션을 사용하는 방법에 대한 자세한 내용은 [비활성 상태 중 마우스 상호 작용 제공](../../mfc/providing-mouse-interaction-while-inactive.md)을 참조하십시오.  
  
 **단순 프레임 컨트롤로 사용**  
 컨트롤에 대해 `OLEMISC_SIMPLEFRAME` 비트를 설정하여 컨트롤이 다른 컨트롤의 컨테이너가 되도록 지정합니다.  For more information, on the [MSDN Library](http://go.microsoft.com/fwlink/?linkID=150542) website, search for "Simple Frame Site Containment".  
  
 **비동기적으로 속성 로드**  
 이전 비동기 데이터를 다시 설정할 수 있도록 하고 컨트롤의 비동기 속성의 새 부하를 시작합니다.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)   
 [응용 프로그램 설정, MFC ActiveX 컨트롤 마법사](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [MFC ActiveX 컨트롤 마법사, 컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md)