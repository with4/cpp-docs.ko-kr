---
title: CIPAddressCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
dev_langs:
- C++
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86d6c4cdff533538c2f0ea7f0be1fa44bfd27359
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368916"
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl 클래스
Windows의 공용 IP 주소 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|`CIPAddressCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|IP 주소 컨트롤의 내용을 지웁니다.|  
|[CIPAddressCtrl::Create](#create)|IP 주소 컨트롤을 만들고에 연결 된 `CIPAddressCtrl` 개체입니다.|  
|[CIPAddressCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 IP 주소 컨트롤을 만들고에 연결 된 `CIPAddressCtrl` 개체입니다.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|IP 주소 컨트롤의 모든 4 개의 필드의 주소 값을 검색 합니다.|  
|[CIPAddressCtrl::IsBlank](#isblank)|IP 주소 컨트롤의 모든 필드가 비어 있는 경우를 결정 합니다.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|IP 주소 컨트롤에서 4 개의 필드에 대 한 주소 값을 설정합니다.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|IP 주소 컨트롤에 지정된 된 필드를 키보드 포커스를 설정합니다.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|IP 주소 컨트롤의 지정된 된 필드에 범위를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 편집 컨트롤을 비슷한은 IP 주소 컨트롤을 입력 하 고 IP (인터넷 프로토콜) 형식으로 숫자 주소를 조작할 수 있습니다.  
  
 이 컨트롤 (및 따라서는 `CIPAddressCtrl` 클래스) 및 이후 버전 Internet Explorer 4.0에서 실행 되는 프로그램에만 사용할 수 있습니다. 또한 이후 버전의 Windows 및 Windows NT에서 사용할 수 있습니다.  
  
 IP 주소 컨트롤에 대 한 자세한 내용은 참조 하십시오. [IP 주소 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb761372) Windows sdk에서입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="cipaddressctrl"></a>  CIPAddressCtrl::CIPAddressCtrl  
 
          `CIPAddressCtrl` 개체를 만듭니다.  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="clearaddress"></a>  CIPAddressCtrl::ClearAddress  
 IP 주소 컨트롤의 내용을 지웁니다.  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="create"></a>  CIPAddressCtrl::Create  
 IP 주소 컨트롤을 만들고에 연결 된 `CIPAddressCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 IP 주소 컨트롤의 스타일입니다. 창 스타일의 조합을 적용 됩니다. 포함 해야 합니다는 **WS_CHILD** 컨트롤을 자식 창 이어야 하므로 스타일입니다. 참조 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 창 스타일의 목록을 Windows sdk입니다.  
  
 `rect`  
 IP 주소 컨트롤의 크기와 위치에 대 한 참조입니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다.  
  
 `pParentWnd`  
 IP 주소 컨트롤의 부모 창에 대 한 포인터입니다. 않아야 **NULL입니다.**  
  
 `nID`  
 IP 주소 컨트롤의 id입니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CIPAddressCtrl` 두 단계를 수행에서 하는 개체입니다.  
  
1.  만드는 생성자를 호출 하는 `CIPAddressCtrl` 개체입니다.  
  
2.  호출 **만들기**, IP 주소 컨트롤 만듭니다.  
  
 컨트롤 확장된 창 스타일을 사용 하려면 호출 [CreateEx](#createex) 대신 **만들기**합니다.  
  
##  <a name="createex"></a>  CIPAddressCtrl::CreateEx  
 컨트롤 (자식 창)을 만들고 사용 하 여 연결 하려면이 함수를 호출 하 여 `CIPAddressCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
 `dwStyle`  
 IP 주소 컨트롤의 스타일입니다. 창 스타일의 조합을 적용 됩니다. 포함 해야 합니다는 **WS_CHILD** 컨트롤을 자식 창 이어야 하므로 스타일입니다. 참조 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 창 스타일의 목록을 Windows sdk입니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_** 합니다.  
  
##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress  
 IP 주소 컨트롤의 모든 4 개의 필드의 주소 값을 검색 합니다.  
  
```  
int GetAddress(
    BYTE& nField0,  
    BYTE& nField1,  
    BYTE& nField2,  
    BYTE& nField3);  
  
int GetAddress(DWORD& dwAddress);
```  
  
### <a name="parameters"></a>매개 변수  
 `nField0`  
 압축 된 IP 주소에서 0 필드 값에 대 한 참조입니다.  
  
 `nField1`  
 압축 된 IP 주소에서 1 필드 값에 대 한 참조입니다.  
  
 `nField2`  
 압축 된 IP 주소에서 2 필드 값에 대 한 참조입니다.  
  
 `nField3`  
 압축 된 IP 주소에서 3 필드 값에 대 한 참조입니다.  
  
 `dwAddress`  
 주소에 대 한 참조는 `DWORD` IP 주소를 수신 하는 값입니다. 참조 **주의** 표시 하는 테이블에 대 한 방법을 `dwAddress` 채워집니다.  
  
### <a name="return-value"></a>반환 값  
 IP 주소 컨트롤의 비어 있지 않은 필드의 수입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378)Windows SDK에 설명 된 대로 합니다. 위의 첫 번째 프로토타입의 읽을 숫자 0-3 컨트롤의 필드를 왼쪽에서 오른쪽 각각, 4 개의 매개 변수를 채웁니다. 위의 두 번째 프로토타입의 `dwAddress` 는 다음과 같이 채워집니다.  
  
|필드|필드 값을 포함 하는 비트|  
|-----------|-------------------------------------|  
|0|-31 24|  
|1|부터 23까지 16|  
|2|8 ~ 15|  
|3|0 ~ 7|  
  
##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank  
 IP 주소 컨트롤의 모든 필드가 비어 있는 경우를 결정 합니다.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>반환 값  
 모든 경우에 0이 아닌 IP 주소 컨트롤의 필드가 비어 있습니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="setaddress"></a>  CIPAddressCtrl::SetAddress  
 IP 주소 컨트롤에서 4 개의 필드에 대 한 주소 값을 설정합니다.  
  
```  
void SetAddress(
    BYTE nField0,  
    BYTE nField1,  
    BYTE nField2,  
    BYTE nField3);  
  
void SetAddress(DWORD dwAddress);
```  
  
### <a name="parameters"></a>매개 변수  
 `nField0`  
 압축 된 IP 주소에서 0 필드 값입니다.  
  
 `nField1`  
 압축 된 IP 주소에서 1 필드 값입니다.  
  
 `nField2`  
 압축 된 IP 주소에서 2 필드 값입니다.  
  
 `nField3`  
 압축 된 IP 주소에서 3 필드 값입니다.  
  
 `dwAddress`  
 A `DWORD` 새 IP 주소를 포함 하는 값입니다. 참조 **주의** 표시 하는 테이블에 대 한 방법을 `DWORD` 값은 채워집니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380)Windows SDK에 설명 된 대로 합니다. 위의 첫 번째 프로토타입의 읽을 숫자 0-3 컨트롤의 필드를 왼쪽에서 오른쪽 각각, 4 개의 매개 변수를 채웁니다. 위의 두 번째 프로토타입의 `dwAddress` 는 다음과 같이 채워집니다.  
  
|필드|필드 값을 포함 하는 비트|  
|-----------|-------------------------------------|  
|0|-31 24|  
|1|부터 23까지 16|  
|2|8 ~ 15|  
|3|0 ~ 7|  
  
##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus  
 IP 주소 컨트롤에 지정된 된 필드를 키보드 포커스를 설정합니다.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>매개 변수  
 `nField`  
 포커스를 설정할 수는 0부터 시작 필드 인덱스입니다. 이 값 필드의 수보다 큰 경우 첫 번째 빈 필드에 포커스가 설정 됩니다. 모든 필드가 비어 있지 않은 경우 첫 번째 필드에 포커스가 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="setfieldrange"></a>  CIPAddressCtrl::SetFieldRange  
 IP 주소 컨트롤의 지정된 된 필드에 범위를 설정합니다.  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>매개 변수  
 `nField`  
 범위 적용 될 0부터 시작 필드 인덱스입니다.  
  
 `nLower`  
 이 IP 주소 컨트롤의 지정된 된 필드의 하 한을 수신 하는 정수에 대 한 참조입니다.  
  
 `nUpper`  
 이 IP 주소 컨트롤의 지정된 된 필드의 상한값을 수신 하는 정수에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382)Windows SDK에 설명 된 대로 합니다. 두 개의 매개 변수를 사용 하 여 `nLower` 및 `nUpper`대신 필드의 아래쪽과 위쪽 한계를 나타내기 위해는 *wRange* Win32 메시지와 함께 사용 되는 매개 변수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



