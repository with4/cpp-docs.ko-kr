---
title: "CNetAddressCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CNetAddressCtrl class
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 03b08d13a9e456c5533b4dddce7f389a63a69c6d
ms.lasthandoff: 02/24/2017

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
|[CNetAddressCtrl::CreateEx](#createex)|확장된 스타일을 지정된 하 여 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|사용자가 현재 네트워크 주소 컨트롤에서 지원 되지 않는 네트워크 주소를 입력 한 오류 풍선 설명을 표시 합니다.|  
|[CNetAddressCtrl::GetAddress](#getaddress)|현재 네트워크 주소 컨트롤에 연결 된 네트워크 주소의 유효성을 검사 하 고 구문 분석 된 표현을 검색 합니다.|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 검색 합니다.|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 설정 합니다.|  
  
## <a name="remarks"></a>주의  
 네트워크 주소 컨트롤 사용자가 입력 주소 형식이 올바른지 확인 합니다. 컨트롤의 네트워크 주소에 실제로 연결 되지 않습니다. [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드 하나 이상의 유형의 주소를 지정 하는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드 구문 분석 하 고 확인할 수 있습니다. 주소는 IPv4, IPv6, 또는 서버, 네트워크, 호스트 또는 브로드캐스트 메시지 대상에 대 한 명명 된 주소 형식일 수 있습니다. 사용할 수 있습니다 주소 형식이 올바르지 않으면는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 메서드를 그래픽으로 네트워크 주소 컨트롤의 텍스트 상자를 가리키는 하 고 미리 정의 된 오류 메시지를 표시 하는 정보 팁 메시지 상자를 표시 합니다.  
  
 `CNetAddressCtrl` 에서 파생 된 클래스는 [CEdit](../../mfc/reference/cedit-class.md) 클래스입니다. 따라서 네트워크 주소 컨트롤 모든 Windows 편집 컨트롤 메시지에 대 한 액세스를 제공합니다.  
  
 다음 그림은 네트워크 주소 컨트롤을 포함 하는 대화 상자를 보여 줍니다. 텍스트 상자 (1) 네트워크 주소 컨트롤에 대 한 잘못 된 네트워크 주소를 포함합니다. 정보 팁 메시지 (2)는 네트워크 주소가 올바르지 않습니다. 경우에 표시 됩니다.  
  
 ![네트워크 주소 컨트롤 및 정보 팁이 있는 대화 상자입니다. ] (../../mfc/reference/media/cnetaddctrl.png "cnetaddctrl")  
  
## <a name="example"></a>예제  
 다음 코드 예제는 네트워크 주소 유효성을 검사 하는 대화의 일부입니다. 세 개의 라디오 단추에 대 한 이벤트 처리기는 네트워크 주소 중 하나일 수 있습니다 세 가지 주소 형식 지정 합니다. 사용자가 네트워크 컨트롤의 텍스트 상자에는 주소를 입력 한 다음 주소 유효성을 검사 하는 단추를 누를 합니다. 해당 주소가 유효한 경우 성공 메시지가 표시 됩니다. 그렇지 않으면 미리 정의 된 정보 팁 오류 메시지가 표시 됩니다.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>예제  
 대화 헤더 파일에서 다음 코드 예제는 [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) 및 [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) 에서 필요로 하는 변수는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s&#1;&2;](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
 이 클래스에서 지원 됩니다 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 이상.  
  
 이 클래스에 대 한 추가 요구 사항에 설명 되어 [빌드 요구 사항에 대 한 Windows Vista 공용 컨트롤](../../mfc/build-requirements-for-windows-vista-common-controls.md)합니다.  
  
##  <a name="a-namecnetaddressctrla--cnetaddressctrlcnetaddressctrl"></a><a name="cnetaddressctrl"></a>CNetAddressCtrl::CNetAddressCtrl  
 `CNetAddressCtrl` 개체를 생성합니다.  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>주의  
 사용 된 [CNetAddressCtrl::Create](#create) 또는 [CNetAddressCtrl::CreateEx](#createex) 네트워크 컨트롤을 만들고에 연결 하는 메서드는 `CNetAddressCtrl` 개체입니다.  
  
##  <a name="a-namecreatea--cnetaddressctrlcreate"></a><a name="create"></a>CNetAddressCtrl::Create  
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
|[in] `dwStyle`|컨트롤에 적용 될 스타일의 비트 조합입니다. 자세한 내용은 참조 [스타일 편집](../../mfc/reference/edit-styles.md)합니다.|  
|[in] `rect`|에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 컨트롤의 크기와 위치를 포함 하는 구조입니다.|  
|[in] `pParentWnd`|에 대 한 null이 아닌 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체 컨트롤의 부모 창입니다.|  
|[in] `nID`|컨트롤의 ID입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="a-namecreateexa--cnetaddressctrlcreateex"></a><a name="createex"></a>CNetAddressCtrl::CreateEx  
 확장된 스타일을 지정된 하 여 네트워크 주소 컨트롤을 만들고 현재 연결 `CNetAddressCtrl` 개체입니다.  
  
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
|[in] `dwExStyle`|확장된 스타일을 컨트롤에 적용할 수의 비트 조합 (OR)입니다. 자세한 내용은 참조는 `dwExStyle` 의 매개 변수는 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 함수입니다.|  
|[in] `dwStyle`|컨트롤에 적용 될 스타일의 비트 조합 (OR)입니다. 자세한 내용은 참조 [스타일 편집](../../mfc/reference/edit-styles.md)합니다.|  
|[in] `rect`|에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 컨트롤의 크기와 위치를 포함 하는 구조입니다.|  
|[in] `pParentWnd`|에 대 한 null이 아닌 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체 컨트롤의 부모 창입니다.|  
|[in] `nID`|컨트롤의 ID입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
##  <a name="a-namedisplayerrortipa--cnetaddressctrldisplayerrortip"></a><a name="displayerrortip"></a>CNetAddressCtrl::DisplayErrorTip  
 현재 네트워크 주소 컨트롤에 연결 하 여 풍선 설명의 오류 메시지를 표시 합니다.  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>반환 값  
 값 `S_OK` 이 메서드가 되 고, 그렇지 않으면 오류 코드가 있습니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여는 [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드를 현재 네트워크 주소 컨트롤을 지원할 수 있는 주소 유형을 지정 합니다. 사용 하는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 유효성 검사 및 사용자가 입력 하는 네트워크 주소를 구문 분석 합니다. 사용 하 여는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 경우 오류 메시지 정보 팁을 표시 하려면 메서드는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드는 성공 하지 않습니다.  
  
 호출 하는이 메시지는 [NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314) 에 설명 된 매크로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 해당 매크로 보냅니다는 `NCM_DISPLAYERRORTIP` 메시지입니다.  
  
##  <a name="a-namegetaddressa--cnetaddressctrlgetaddress"></a><a name="getaddress"></a>CNetAddressCtrl::GetAddress  
 현재 네트워크 주소 컨트롤에 연관 된 네트워크 주소 유효성을 검사 하 고 구문 분석 된 표현을 검색 합니다.  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in, out] `pAddress`|에 대 한 포인터는 [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) 구조입니다.  설정의 `pAddrInfo` 의 주소에이 구조체의 멤버는 [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) GetAddress 메서드를 호출 하기 전에 구조체입니다.|  
  
### <a name="return-value"></a>반환 값  
 값 `S_OK` 이 메서드가 되 고, 그렇지 않으면 COM 오류 코드입니다. 가능한 오류 코드에 대 한 자세한 내용은 반환 값 섹션을 참조는 [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) 매크로입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 성공적으로 수행 되는 [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) 구조 네트워크 주소에 대 한 추가 정보를 포함 합니다.  
  
 사용 하는 [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드는 현재 네트워크 주소를 지원할 수 있는 주소의 유형을 지정 합니다. 사용 하는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 유효성 검사 및 사용자가 입력 하는 네트워크 주소를 구문 분석 합니다. 사용 하 여는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 경우 오류 메시지 정보 팁을 표시 하려면 메서드는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드는 성공 하지 않습니다.  
  
 이 메서드를 호출의 [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) 에 설명 된 매크로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 해당 매크로 보냅니다는 `NCM_GETADDRESS` 메시지입니다.  
  
##  <a name="a-namegetallowtypea--cnetaddressctrlgetallowtype"></a><a name="getallowtype"></a>CNetAddressCtrl::GetAllowType  
 현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 검색 합니다.  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 비트 조합 (OR) 플래그 주소 유형을 지정 하는 네트워크 주소 컨트롤을 지원할 수 있습니다. 자세한 내용은 참조 [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586)합니다.  
  
### <a name="remarks"></a>주의  
 호출 하는이 메시지는 [NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318) 에 설명 된 매크로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 해당 매크로 보냅니다는 `NCM_GETALLOWTYPE` 메시지입니다.  
  
##  <a name="a-namesetallowtypea--cnetaddressctrlsetallowtype"></a><a name="setallowtype"></a>CNetAddressCtrl::SetAllowType  
 현재 네트워크 주소 컨트롤을 지원할 수 있는 네트워크 주소 유형을 설정 합니다.  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `dwAddrMask`|비트 조합 (OR) 플래그 주소 유형을 지정 하는 네트워크 주소 컨트롤을 지원할 수 있습니다. 자세한 내용은 참조 [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586)합니다.|  
  
### <a name="return-value"></a>반환 값  
 `S_OK`이 메서드는 성공 하는 경우 그렇지 않으면 COM 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여는 [CNetAddressCtrl::SetAllowType](#setallowtype) 메서드를 현재 네트워크 주소 컨트롤을 지원할 수 있는 주소 유형을 지정 합니다. 사용 하는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드를 유효성 검사 및 사용자가 입력 하는 네트워크 주소를 구문 분석 합니다. 사용 하 여는 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) 경우 오류 메시지 정보 팁을 표시 하려면 메서드는 [CNetAddressCtrl::GetAddress](#getaddress) 메서드는 성공 하지 않습니다.  
  
 호출 하는이 메시지는 [NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320) 에 설명 된 매크로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 해당 매크로 보냅니다는 `NCM_SETALLOWTYPE` 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CNetAddressCtrl 클래스](../../mfc/reference/cnetaddressctrl-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)

