---
title: CMFCDesktopAlertWndInfo 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb682236f41294b7d14f5950ed7906832dd7d8a2
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038092"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo 클래스
`CMFCDesktopAlertWndInfo` 클래스와 함께 사용 되는 [CMFCDesktopAlertWnd 클래스](../../mfc/reference/cmfcdesktopalertwnd-class.md)합니다. 바탕 화면 경고 창이 표시될 경우 표시되는 컨트롤을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|표시 되는 아이콘에 대 한 핸들입니다.|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|바탕 화면 경고 창이에서 링크와 관련 된 명령 ID입니다.|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|바탕 화면 경고 창이에 표시 되는 텍스트입니다.|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|바탕 화면 경고 창이에 표시 되는 링크입니다.|  
  
## <a name="remarks"></a>설명  
 `CMFCDesktopAlertWndInfo` 클래스에 전달 되는 [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 바탕 화면 경고 창이의 기본 대화 상자에 표시 되는 요소를 지정 하는 메서드. 기본 대화 상자는 세 가지 항목을 포함할 수 있습니다.  
  
-   호출 하 여 설정 하는 아이콘이 [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)합니다.  
  
-   레이블 또는 문자 메시지를 호출 하 여 설정 된 [CMFCDesktopAlertWndInfo::m_strText](#m_strtext)합니다.  
  
-   호출 하 여 설정 된 링크 [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)합니다. 링크를 클릭할 때 실행 되는 명령을 설정 하려면 호출 [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)합니다.  
  
 기본 대화 상자 충분 하지 않은 경우 사용자 지정 대화 상자를 만들 있고에 전달 된 [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 이 클래스를 사용 하는 대신 메서드. 자세한 내용은 참조 [CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는에서 다양 한 멤버를 사용 하 여 `CMFCDesktopAlertWndInfo` 클래스입니다. 바탕 화면 경고 창이, 바탕 화면 경고 창이에 표시 되는 링크 및 바탕 화면 경고 창이에서 링크와 연결 된 명령 ID에 표시 되는 텍스트 아이콘 표시 되는 핸들을 설정 하는 방법을 보여가 줍니다. 이 예제는의 일부는 [바탕 화면 경고 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxDesktopAlertDialog.h  
  
##  <a name="operator_eq"></a>  CMFCDesktopAlertWndInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *src*  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_hicon"></a>  CMFCDesktopAlertWndInfo::m_hIcon  
 표시 되는 아이콘에 대 한 핸들입니다.  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_nurlcmdid"></a>  CMFCDesktopAlertWndInfo::m_nURLCmdID  
 바탕 화면 경고 창이에서 링크와 관련 된 명령 ID입니다.  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>설명  
 명령 ID로 지정 된 링크를 클릭할 때 팝업 창의 소유자에 게 전송 되 [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)합니다.  
  
##  <a name="m_strtext"></a>  CMFCDesktopAlertWndInfo::m_strText  
 바탕 화면 경고 창이에 표시 되는 텍스트입니다.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_strurl"></a>  CMFCDesktopAlertWndInfo::m_strURL  
 바탕 화면 경고 창이에 표시 되는 링크입니다.  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>설명  
 사용자가 링크를 클릭 하면 명령이 있는 [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) 명령 ID가 팝업 창의 소유자에 게 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd 클래스](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [Cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)
