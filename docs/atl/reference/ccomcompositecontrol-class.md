---
title: "CComCompositeControl Class | Microsoft Docs"
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
  - "CComCompositeControl"
  - "ATL::CComCompositeControl"
  - "ATL.CComCompositeControl<T>"
  - "ATL.CComCompositeControl"
  - "ATL::CComCompositeControl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCompositeControl class"
  - "복합 컨트롤, CComCompositeControl class"
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCompositeControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 복합 컨트롤을 구현 하는 데 필요한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T   
>  
class CComCompositeControl :  
public CComControl< T, CAxDialogImpl< T > >  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 복합 컨트롤을 지원 하 고 다른 인터페이스에서 잘 때.  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComCompositeControl::CComCompositeControl](../Topic/CComCompositeControl::CComCompositeControl.md)|생성자입니다.|  
|[CComCompositeControl::~CComCompositeControl](../Topic/CComCompositeControl::~CComCompositeControl.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md)|조언 또는 바이 복합 컨트롤에 의해 호스팅되는 모든 컨트롤에이 메서드를 호출 합니다.|  
|[CComCompositeControl::CalcExtent](../Topic/CComCompositeControl::CalcExtent.md)|크기를 계산 하려면이 메서드를 호출  **HIMETRIC** 복합 컨트롤을 호스팅하는 데 사용 된 대화 상자 리소스의 단위입니다.|  
|[CComCompositeControl::Create](../Topic/CComCompositeControl::Create.md)|합성 컨트롤의 컨트롤 창을 만들려면이 메서드가 호출 됩니다.|  
|[CComCompositeControl::CreateControlWindow](../Topic/CComCompositeControl::CreateControlWindow.md)|제어 창을 만들고 알리기 호스팅된 컨트롤에이 메서드를 호출 합니다.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](../Topic/CComCompositeControl::SetBackgroundColorFromAmbient.md)|컨테이너의 배경색을 사용 하 여 합성 컨트롤의 배경색을 설정 하려면이 메서드를 호출 합니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CComCompositeControl::m\_hbrBackground](../Topic/CComCompositeControl::m_hbrBackground.md)|배경 브러시입니다.|  
|[CComCompositeControl::m\_hWndFocus](../Topic/CComCompositeControl::m_hWndFocus.md)|현재 포커스가 있는 창의 핸들입니다.|  
  
## 설명  
 파생 클래스에서 `CComCompositeControl` ActiveX 합성 컨트롤의 기능을 상속 합니다.  ActiveX 컨트롤에서 파생 된 `CComCompositeControl` 표준 대화 상자에 호스팅됩니다.  \(네이티브 Windows 컨트롤 및 ActiveX 컨트롤\) 다른 컨트롤을 호스팅할 수 있기 때문에 이러한 종류의 컨트롤 합성 컨트롤 이라고 합니다.  
  
 `CComCompositeControl`합성 컨트롤은 자식 클래스에 열거형된 데이터 멤버에 대 한 보고 만드는 데 사용할 대화 상자 리소스를 식별 합니다.  IDD이 자식 클래스의 멤버가 컨트롤의 창으로 사용 되는 대화 상자 리소스의 리소스 ID로 설정 됩니다.  다음 클래스에서 파생 된 데이터 멤버의 예로 `CComCompositeControl` 컨트롤의 창에 사용할 대화 상자 리소스를 식별할 수 있어야 합니다.  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/CPP/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  창 없는 컨트롤을 포함할 수는 있지만 합성 컨트롤에서 항상 창 컨트롤입니다.  
  
 컨트롤에 의해 구현 된 `CComCompositeControl`\-파생된 클래스에 기본 내장 된 동작 탭 이동 합니다.  포함 하는 응용 프로그램에서 탭 하 여 컨트롤이 포커스를 받을 때 TAB 키를 누르면 연속적으로 모든 합성 컨트롤의 포함 된 컨트롤을 합성 컨트롤에서 다음 및 컨테이너의 탭 순서에서 다음 항목에 순환할 수 나가게 됩니다.  호스팅된 컨트롤의 탭 순서 대화 상자 리소스에 의해 결정 되며 순서 결정 어떤 탭에서 발생 합니다.  
  
> [!NOTE]
>  올바로 작동 하려면 액셀러레이터 키를는 `CComCompositeControl`, 컨트롤을 만들 때 액셀러레이터 키 테이블을 로드, 핸들과 액셀러레이터 키로 다시 개수를 전달 하는 데 필요한 됩니다  [IOleControlImpl::GetControlInfo](../Topic/IOleControlImpl::GetControlInfo.md), 마지막으로 컨트롤을 놓을 때 테이블을 삭제 하.  
  
## 예제  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/CPP/ccomcompositecontrol-class_2.h)]  
  
## 상속 계층 구조  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [합성 컨트롤 기본 사항](../../atl/atl-composite-control-fundamentals.md)   
 [Class Overview](../../atl/atl-class-overview.md)