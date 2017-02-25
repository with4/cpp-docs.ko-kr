---
title: "CStockPropImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStockPropImpl"
  - "ATL::CStockPropImpl"
  - "ATL.CStockPropImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[ATL], 스톡 속성"
  - "CStockPropImpl class"
  - "스톡 속성, ATL 컨트롤"
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CStockPropImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 지 원하는 스톡 속성 값에 대 한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
class InterfaceName,   
const IID* piid= &_ATL_IIDOF(InterfaceName),   
const GUID* plibid= &CComModule::m_libid,   
WORD wMajor= 1,  
WORD wMinor= 0,   
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE CStockPropImpl :  
public IDispatchImpl< InterfaceName, piid, plibid, wMajor,  
   wMinor, tihclass>  
```  
  
#### 매개 변수  
 `T`  
 컨트롤을 구현 하 고 파생 클래스 `CStockPropImpl`.  
  
 `InterfaceName`  
 스톡 속성을 노출 하는 이중 인터페이스입니다.  
  
 `piid`  
 IID에 대 한 포인터 `InterfaceName`.  
  
 `plibid`  
 포인터의 정의를 포함 하는 형식 라이브러리의 LIBID `InterfaceName`.  
  
 `wMajor`  
 형식 라이브러리의 주 버전입니다.  기본값은 1입니다.  
  
 `wMinor`  
 형식 라이브러리의 부 버전입니다.  기본값은 0입니다.  
  
 `tihclass`  
 클래스의 형식 정보를 관리 하는 데 `T`.  기본값은 `CComTypeInfoHolder`입니다.  
  
## Members  
  
### Public 메서드  
  
|||  
|-|-|  
|[get\_Appearance](../Topic/CStockPropImpl::get_Appearance.md)|이 메서드는 컨트롤에서 사용 되는 예를 들어, 플랫 페인트 스타일 나 3d를 호출 합니다.|  
|[get\_AutoSize](../Topic/CStockPropImpl::get_AutoSize.md)|컨트롤 다른 크기는 없는 경우를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|  
|[get\_BackColor](../Topic/CStockPropImpl::get_BackColor.md)|컨트롤의 배경색을 가져오려면이 메서드를 호출 합니다.|  
|[get\_BackStyle](../Topic/CStockPropImpl::get_BackStyle.md)|컨트롤의 배경 스타일을 투명 하거나 불투명 하 게 하려면이 메서드를 호출 합니다.|  
|[get\_BorderColor](../Topic/CStockPropImpl::get_BorderColor.md)|컨트롤의 테두리 색을 가져오려면이 메서드를 호출 합니다.|  
|[get\_BorderStyle](../Topic/CStockPropImpl::get_BorderStyle.md)|컨트롤의 테두리 스타일을 가져오려면이 메서드를 호출 합니다.|  
|[get\_BorderVisible](../Topic/CStockPropImpl::get_BorderVisible.md)|컨트롤의 테두리가 표시 되는지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|  
|[get\_BorderWidth](../Topic/CStockPropImpl::get_BorderWidth.md)|컨트롤의 테두리 너비를 픽셀 단위로 가져오려면이 메서드를 호출 합니다.|  
|[get\_Caption](../Topic/CStockPropImpl::get_Caption.md)|텍스트를 개체의 캡션을 지정 하려면이 메서드를 호출 합니다.|  
|[get\_DrawMode](../Topic/CStockPropImpl::get_DrawMode.md)|컨트롤의 그리기 모드를 XOR 펜 또는 색 반전 예를 들어,이 메서드를 호출 합니다.|  
|[get\_DrawStyle](../Topic/CStockPropImpl::get_DrawStyle.md)|예를 들어,이 메서드는 컨트롤의 그리기 스타일을 실선, 파선 또는 점선를 호출 합니다.|  
|[get\_DrawWidth](../Topic/CStockPropImpl::get_DrawWidth.md)|사용 하 여 드로잉 메서드는 컨트롤의 그리기 너비 픽셀 단위로 가져오려면이 메서드를 호출 합니다.|  
|[get\_Enabled](../Topic/CStockPropImpl::get_Enabled.md)|컨트롤의 사용 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|  
|[get\_FillColor](../Topic/CStockPropImpl::get_FillColor.md)|컨트롤의 채우기 색을 가져오려면이 메서드를 호출 합니다.|  
|[get\_FillStyle](../Topic/CStockPropImpl::get_FillStyle.md)|예를 들어,이 메서드는 컨트롤의 채우기 스타일을 단색, 투명 또는 빗금이 호출 합니다.|  
|[get\_Font](../Topic/CStockPropImpl::get_Font.md)|포인터를 컨트롤의 글꼴 속성을 가져오려면이 메서드를 호출 합니다.|  
|[get\_ForeColor](../Topic/CStockPropImpl::get_ForeColor.md)|컨트롤의 전경색을 가져오려면이 메서드를 호출 합니다.|  
|[get\_HWND](../Topic/CStockPropImpl::get_HWND.md)|컨트롤과 연결 된 창 핸들을 가져오도록이 메서드를 호출 합니다.|  
|[get\_MouseIcon](../Topic/CStockPropImpl::get_MouseIcon.md)|그림 속성 \(아이콘, 비트맵, 또는 메타 파일\) 마우스를 컨트롤 위에 있을 때 표시 되는 그래픽을 가져오려면이 메서드를 호출 합니다.|  
|[get\_MousePointer](../Topic/CStockPropImpl::get_MousePointer.md)|마우스 포인터를 컨트롤 위에 마우스를 예를 들어 있을 때 표시, 화살표, 간, 또는 모래의 종류를 얻으려면이 메서드를 호출 합니다.|  
|[get\_Picture](../Topic/CStockPropImpl::get_Picture.md)|그림 속성 \(아이콘, 비트맵, 또는 메타 파일\) 표시 하는 그래픽에 포인터를 가져오려면이 메서드를 호출 합니다.|  
|[get\_ReadyState](../Topic/CStockPropImpl::get_ReadyState.md)|예를 들어,이 메서드는 컨트롤 상태가 로드 또는 로드를 호출 합니다.|  
|[get\_TabStop](../Topic/CStockPropImpl::get_TabStop.md)|컨트롤 탭 정지 인지 여부를 나타내는 플래그를 가져오려면이 메서드를 호출 합니다.|  
|[get\_Text](../Topic/CStockPropImpl::get_Text.md)|텍스트를 컨트롤에 표시 되는이 메서드를 호출 합니다.|  
|[get\_Valid](../Topic/CStockPropImpl::get_Valid.md)|컨트롤이 유효한 지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|  
|[get\_Window](../Topic/CStockPropImpl::get_Window.md)|컨트롤과 연결 된 창 핸들을 가져오도록이 메서드를 호출 합니다.  동일한  [CStockPropImpl::get\_HWND](../Topic/CStockPropImpl::get_HWND.md).|  
|[put\_Appearance](../Topic/CStockPropImpl::put_Appearance.md)|컨트롤에서 사용 되는 예를 들어, 플랫 페인트 스타일 또는 3d를 설정 하려면이 메서드를 호출 합니다.|  
|[put\_AutoSize](../Topic/CStockPropImpl::put_AutoSize.md)|컨트롤 다른 크기는 없는 경우를 나타내는 플래그 값을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_BackColor](../Topic/CStockPropImpl::put_BackColor.md)|컨트롤의 배경색을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_BackStyle](../Topic/CStockPropImpl::put_BackStyle.md)|컨트롤의 배경 스타일을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_BorderColor](../Topic/CStockPropImpl::put_BorderColor.md)|컨트롤의 테두리 색을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_BorderStyle](../Topic/CStockPropImpl::put_BorderStyle.md)|컨트롤의 테두리 스타일을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_BorderVisible](../Topic/CStockPropImpl::put_BorderVisible.md)|컨트롤의 테두리가 표시 되는지 여부를 나타내는 플래그 값을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_BorderWidth](../Topic/CStockPropImpl::put_BorderWidth.md)|컨트롤의 테두리 너비를 설정 하려면이 메서드를 호출 합니다.|  
|[put\_Caption](../Topic/CStockPropImpl::put_Caption.md)|컨트롤에 표시할 텍스트를 설정 하려면이 메서드를 호출 합니다.|  
|[put\_DrawMode](../Topic/CStockPropImpl::put_DrawMode.md)|예를 들어, XOR 펜 또는 색 반전 컨트롤의 그리기 모드를 설정 하려면이 메서드를 호출 합니다.|  
|[put\_DrawStyle](../Topic/CStockPropImpl::put_DrawStyle.md)|이 메서드는 컨트롤의 그리기 스타일을 설정 하는 예를 들어, 실선, 파선 또는 점선 호출 합니다.|  
|[put\_DrawWidth](../Topic/CStockPropImpl::put_DrawWidth.md)|사용 하 여 드로잉 메서드는 컨트롤의 너비를 픽셀 단위로 설정 하려면이 메서드를 호출 합니다.|  
|[put\_Enabled](../Topic/CStockPropImpl::put_Enabled.md)|컨트롤의 사용 여부를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.|  
|[put\_FillColor](../Topic/CStockPropImpl::put_FillColor.md)|컨트롤의 채우기 색을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_FillStyle](../Topic/CStockPropImpl::put_FillStyle.md)|이 메서드는 컨트롤의 채우기 스타일을 설정 하는 예를 들어, 단색, 투명 또는 빗금이 호출 합니다.|  
|[put\_Font](../Topic/CStockPropImpl::put_Font.md)|컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_ForeColor](../Topic/CStockPropImpl::put_ForeColor.md)|컨트롤의 전경색을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_HWND](../Topic/CStockPropImpl::put_HWND.md)|E\_FAIL이 반환 됩니다.|  
|[put\_MouseIcon](../Topic/CStockPropImpl::put_MouseIcon.md)|\(아이콘, 비트맵, 또는 메타 파일\) 마우스를 컨트롤 위에 있을 때 표시 되는 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_MousePointer](../Topic/CStockPropImpl::put_MousePointer.md)|마우스 포인터가 컨트롤 위에 마우스를 예를 들어 있을 때 표시, 화살표, 간, 또는 모래의 종류를 설정 하려면이 메서드를 호출 합니다.|  
|[put\_Picture](../Topic/CStockPropImpl::put_Picture.md)|\(아이콘, 비트맵, 또는 메타 파일\) 표시 하는 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_ReadyState](../Topic/CStockPropImpl::put_ReadyState.md)|예를 들어,이 메서드는 컨트롤의 준비 상태를 설정 하려면 로드 또는 로드를 호출 합니다.|  
|[put\_TabStop](../Topic/CStockPropImpl::put_TabStop.md)|컨트롤 탭 정지 인지 여부를 나타내는 플래그 값을 설정 하려면이 메서드를 호출 합니다.|  
|[put\_Text](../Topic/CStockPropImpl::put_Text.md)|컨트롤에 표시 되는 텍스트를 설정 하려면이 메서드를 호출 합니다.|  
|[put\_Valid](../Topic/CStockPropImpl::put_Valid.md)|컨트롤이 유효한 지 여부를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.|  
|[put\_Window](../Topic/CStockPropImpl::put_Window.md)|이 메서드를 호출 합니다.  [CStockPropImpl::put\_HWND](../Topic/CStockPropImpl::put_HWND.md), E\_FAIL을 반환 합니다.|  
|[putref\_Font](../Topic/CStockPropImpl::putref_Font.md)|참조 횟수를 컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[putref\_MouseIcon](../Topic/CStockPropImpl::putref_MouseIcon.md)|참조 횟수를 \(아이콘, 비트맵, 또는 메타 파일\) 마우스를 컨트롤 위에 있을 때 표시 되는 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|  
|[putref\_Picture](../Topic/CStockPropImpl::putref_Picture.md)|참조 횟수와 그래픽 \(아이콘, 비트맵, 또는 메타 파일\)을 그림 속성을 설정 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CStockPropImpl`제공  **배치** 및  **가져오기** 각 스톡 속성에 대 한 방법.  이러한 방법은 각 속성과 연관 된 데이터 멤버를 가져오거나 설정 하 고 알림 및 속성이 변경 될 때 컨테이너와 동기화 하는 데 필요한 코드를 제공 합니다.  
  
 Visual C\+\+ 해당 마법사에서 스톡 속성을 지원합니다.  스톡 속성을 컨트롤에 추가 하는 방법에 대 한 자세한 내용은  [ATL 자습서](../../atl/active-template-library-atl-tutorial.md).  
  
 이전 버전과 호환성에 대 한 `CStockPropImpl` 도 노출 `get_Window` 및 `put_Window` 메서드를 호출 하면 `get_HWND` 및 `put_HWND`, 각각.  기본 구현의 `put_HWND` 반환  **E\_FAIL** 후 `HWND` 는 읽기 전용 속성 이어야 합니다.  
  
 다음 속성은도  **만 대체 구문이 제공** 구현.  
  
-   글꼴  
  
-   MouseIcon  
  
-   그림  
  
 해당 데이터 멤버 형식으로 같은 세 가지 스톡 속성 필요 `CComPtr` 또는 올바른 인터페이스 참조를 제공 하는 몇 가지 다른 클래스의 대입 연산자를 사용 하 여 계산 합니다.  
  
## 상속 계층 구조  
 `T`  
  
 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)  
  
 `CStockPropImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)