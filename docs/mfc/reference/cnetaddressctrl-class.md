---
title: CNetAddressCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
dev_langs:
- C++
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e80b74262a05548d9aede80df44d204b759b84da
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038518"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl 클래스
`CNetAddressCtrl` 클래스에 입력 한 IPv4, IPv6 및 DNS 주소를 이름이 지정된 형식의 유효성을 검사하는 데 사용할 수 있는 네트워크 주소 컨트롤을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CNetAddressCtrl : public CEdit  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|`CNetAddressCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CNetAddressCtrl::Create](#create)|지정 된 스타일으로 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.|  
|[CNetAddressCtrl::CreateEx](#createex)|지정 된 확장된 스타일을 사용 하 여 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|사용자가 현재 네트워크 주소 컨트롤에서 지원 되지 않는 네트워크 주소를 입력 오류 풍선 설명을 표시 합니다.|  
|[CNetAddressCtrl::GetAddress](#getaddress)|네트워크 주소에 연결 된 현재 네트워크 주소 컨트롤의 유효성을 검사 하 고 구문 분석 된 표현을 검색 합니다.|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 검색 합니다.|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 네트워크 주소 컨트롤 사용자가 입력 주소의 형식을 정확한 지 확인 합니다. 컨트롤에서 네트워크 주소로 실제로 연결 되지 않습니다. [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드 하나 이상의 유형의 주소를 지정 하는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드 구문 분석 하 고 확인할 수 있습니다. 주소는 IPv4, IPv6, 또는 서버, 네트워크, 호스트 또는 브로드캐스트 메시지 대상에 대 한 명명 된 주소 형식의 수 있습니다. 주소의 형식이 잘못 되었습니다, 하는 경우 사용할 수 있습니다는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 미리 정의 된 표시를 그래픽으로 네트워크 주소 컨트롤의 텍스트 상자를 가리키는 정보 팁 메시지 상자를 표시 하는 메서드 오류 메시지입니다.  
  
 `CNetAddressCtrl` 클래스에서 파생 된는 [CEdit](../../mfc/reference/cedit-class.md) 클래스입니다. 따라서 네트워크 주소 컨트롤 모든 Windows 편집 컨트롤 메시지에 대 한 액세스를 제공합니다.  
  
 다음 그림은 네트워크 주소 컨트롤을 포함 하는 대화 상자를 보여 줍니다. 텍스트 상자 (1) 네트워크 주소 컨트롤에 대 한 잘못 된 네트워크 주소가 포함 되어 있습니다. 정보 팁 메시지 (2)는 네트워크 주소에 유효 하지 않을 경우에 표시 됩니다.  
  
 ![네트워크 주소 컨트롤 및 정보 팁 있는 대화 상자. ] (../../mfc/reference/media/cnetaddctrl.png "cnetaddctrl")  
  
## <a name="example"></a>예  
 다음 코드 예제는 네트워크 주소 유효성을 검사 하는 대화의 일부입니다. 세 개의 라디오 단추에 대 한 이벤트 처리기 지정 네트워크 주소 세 가지 주소 유형 중 하나가 될 수 있습니다. 사용자가 네트워크 컨트롤의 텍스트 상자에는 주소를 입력 한 다음 주소의 유효성을 검사 하는 단추를 누를 합니다. 주소는 유효 성공 메시지가 표시 됩니다. 그렇지 않은 경우에 미리 정의 된 정보 팁 오류 메시지가 표시 됩니다.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>예  
 대화 상자 헤더 파일에서 다음 코드 예제에서는 정의 [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) 및 [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) 에서 필요로 하는 변수는 [CNetAddressCtrl::GetAddress](#getaddress)메서드.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
 이 클래스에서 지원 됩니다 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 이상.  
  
 이 클래스에 대 한 추가 요구 사항은 [빌드 요구 사항에 대 한 Windows Vista 공용 컨트롤](../../mfc/build-requirements-for-windows-vista-common-controls.md)합니다.  
  
##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl  
 `CNetAddressCtrl` 개체를 생성합니다.  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>설명  
 사용 하 여는 [CNetAddressCtrl::Create](#create) 또는 [CNetAddressCtrl::CreateEx](#createex) 네트워크 컨트롤을 만들고에 연결 하는 메서드는 `CNetAddressCtrl` 개체입니다.  
  
##  <a name="create"></a>  CNetAddressCtrl::Create  
 지정 된 스타일으로 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *dwStyle*|스타일을 컨트롤에 적용할 수의 비트 조합입니다. 자세한 내용은 참조 [스타일 편집](../../mfc/reference/styles-used-by-mfc.md#edit-styles)합니다.|  
|[in] *rect*|에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 컨트롤의 크기와 위치를 포함 하는 구조입니다.|  
|[in] *pParentWnd*|에 대 한 null이 아닌 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체는 컨트롤의 부모 창입니다.|  
|[in] *nID*|컨트롤의 ID입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="createex"></a>  CNetAddressCtrl::CreateEx  
 지정 된 확장된 스타일을 사용 하 여 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *dwExStyle*|컨트롤에 적용 될 확장된 스타일의 비트 조합 (OR)입니다. 자세한 내용은 참조는 *dwExStyle* 의 매개 변수는 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 함수입니다.|  
|[in] *dwStyle*|스타일을 컨트롤에 적용할 수의 비트 조합 (OR)입니다. 자세한 내용은 참조 [스타일 편집](../../mfc/reference/styles-used-by-mfc.md#edit-styles)합니다.|  
|[in] *rect*|에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 컨트롤의 크기와 위치를 포함 하는 구조입니다.|  
|[in] *pParentWnd*|에 대 한 null이 아닌 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체는 컨트롤의 부모 창입니다.|  
|[in] *nID*|컨트롤의 ID입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip  
 현재 네트워크 주소 컨트롤와 연결 된 풍선 팁에는 오류 메시지를 표시 합니다.  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>반환 값  
 값 `S_OK` 이 메서드가 고, 그러지 않으면 오류 코드가 있습니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여는 [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드는 현재 네트워크 주소 컨트롤을 지원할 수 있는 주소의 유형을 지정 합니다. 사용 하 여는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 확인 하 고 사용자가 입력 하는 네트워크 주소 구문 분석 합니다. 사용 하 여는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 경우 오류 메시지 정보 팁을 표시 하는 메서드는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드는 성공 하지 않습니다.  
  
 이 메시지가 호출 된 [NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314) 매크로 Windows SDK에 설명 되어 있습니다. 매크로 보냅니다는 `NCM_DISPLAYERRORTIP` 메시지입니다.  
  
##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress  
 현재 네트워크 주소 컨트롤와 연결 된 네트워크 주소의 유효성을 검사 하 고 구문 분석 된 표현을 검색 합니다.  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out에서] *pAddress*|에 대 한 포인터는 [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) 구조입니다.  설정의 *pAddrInfo* 의 주소에이 구조체의 멤버는 [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) GetAddress 메서드를 호출 하기 전에 구성 합니다.|  
  
### <a name="return-value"></a>반환 값  
 값 `S_OK` 이 메서드가 성공적 이면 COM 오류 코드가 있습니다. 가능한 오류 코드에 대 한 자세한 내용은의 반환 값 섹션을 참조 하십시오.는 [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) 매크로입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 성공 하는 경우는 [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) 구조 네트워크 주소에 대 한 추가 정보를 포함 합니다.  
  
 사용 하 여는 [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드 주소는 현재 네트워크 주소 컨트롤을 지원할 수의 유형을 지정 합니다. 사용 하 여는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 확인 하 고 사용자가 입력 하는 네트워크 주소 구문 분석 합니다. 사용 하 여는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 경우 오류 메시지 정보 팁을 표시 하는 메서드는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드는 성공 하지 않습니다.  
  
 이 메서드 호출의 [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) 매크로 Windows SDK에 설명 되어 있습니다. 매크로 보냅니다는 `NCM_GETADDRESS` 메시지입니다.  
  
##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType  
 현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 검색 합니다.  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 비트 조합 (OR) 플래그는 두 주소 유형을 지정 하는 네트워크 주소 컨트롤을 지원할 수 있습니다. 자세한 내용은 참조 [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586)합니다.  
  
### <a name="remarks"></a>설명  
 이 메시지가 호출 된 [NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318) 매크로 Windows SDK에 설명 되어 있습니다. 매크로는 NCM_GETALLOWTYPE 메시지를 보냅니다.  
  
##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType  
 현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 설정 합니다.  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *dwAddrMask*|비트 조합 (OR) 플래그는 두 주소 유형을 지정 하는 네트워크 주소 컨트롤을 지원할 수 있습니다. 자세한 내용은 참조 [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586)합니다.|  
  
### <a name="return-value"></a>반환 값  
 `S_OK` 이 메서드는 성공 하는 경우 그렇지 않으면 COM 오류 코드가 있습니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여는 [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드는 현재 네트워크 주소 컨트롤을 지원할 수 있는 주소의 유형을 지정 합니다. 사용 하 여는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 확인 하 고 사용자가 입력 하는 네트워크 주소 구문 분석 합니다. 사용 하 여는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 경우 오류 메시지 정보 팁을 표시 하는 메서드는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드는 성공 하지 않습니다.  
  
 이 메시지가 호출 된 [NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320) 매크로 Windows SDK에 설명 되어 있습니다. 매크로는 NCM_SETALLOWTYPE 메시지를 보냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [CNetAddressCtrl 클래스](../../mfc/reference/cnetaddressctrl-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)
