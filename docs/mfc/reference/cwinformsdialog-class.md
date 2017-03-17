---
title: "CWinFormsDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsDialog class
- Windows Forms [C++], MFC support
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
caps.latest.revision: 26
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
ms.openlocfilehash: 86768a849b0112f7c4f8b6b2a694b80065169575
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog 클래스
Windows Forms 사용자 정의 컨트롤을 호스팅하는 MFC 대화 상자 클래스의 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
    public CDialog  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TManagedControl`  
 MFC 응용 프로그램에 표시 되는.NET Framework 사용자 정의 컨트롤  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|`CWinFormsDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](#getcontrol)|Windows Forms 사용자 정의 컨트롤에 대 한 참조를 검색합니다.|  
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Windows Forms 사용자 정의 컨트롤에 대 한 창 핸들을 검색합니다.|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|MFC 대화 상자를 만들고 호스팅하는 Windows Forms 사용자 정의 컨트롤에 의해 초기화 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|대체 [CWinFormsDialog::GetControl](#getcontrol) 식에 있습니다.|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Windows Forms 사용자 정의 컨트롤에 대 한 참조로 형식을 캐스팅합니다.|  
  
## <a name="remarks"></a>주의  
 `CWinFormsDialog`MFC 대화 상자 클래스에 대 한 래퍼인 ( [CDialog](../../mfc/reference/cdialog-class.md))를 호스팅하는 Windows Forms 사용자 정의 컨트롤입니다. 이.NET Framework는 모달 또는 모덜리스 MFC 대화 상자의 컨트롤에 표시할 수 있습니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 및 [는 Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h  
  
##  <a name="cwinformsdialog"></a>CWinFormsDialog::CWinFormsDialog  
 `CWinFormsDialog` 개체를 생성합니다.  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDTemplate`  
 대화 상자 템플릿 리소스의 ID를 포함 합니다. 대화 상자 편집기를 사용 하 여 대화 상자 템플릿을 만들고 응용 프로그램의 리소스 스크립트 파일에 저장 합니다. 대화 상자 템플릿에 대 한 자세한 내용은 참조 하십시오. [CDialog 클래스](../../mfc/reference/cdialog-class.md)합니다.  
  
##  <a name="getcontrol"></a>CWinFormsDialog::GetControl  
 Windows Forms 사용자 정의 컨트롤에 대 한 참조를 검색합니다.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 MFC 대화 상자에서 Windows Forms 컨트롤에 대 한 참조를 반환합니다.  
  
##  <a name="getcontrolhandle"></a>CWinFormsDialog::GetControlHandle  
 Windows Forms 사용자 정의 컨트롤에 대 한 창 핸들을 검색합니다.  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 Windows Forms 사용자 정의 컨트롤에 대 한 창 핸들을 반환합니다.  
  
##  <a name="oninitdialog"></a>CWinFormsDialog::OnInitDialog  
 MFC 대화 상자를 만들고 호스팅하는 Windows Forms 사용자 정의 컨트롤에 의해 초기화 합니다.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>반환 값  
 설정 여부를 응용 프로그램에 입력된 포커스가 컨트롤 중 하나를 대화 상자에서 지정 하는 부울 값입니다. 경우 `OnInitDialog`&0;이 아닌 반환 Windows 입력된 포커스를 첫 번째 컨트롤로 설정 대화 상자에서 합니다. 이 메서드는 응용 프로그램에 명시적으로 설정에 입력된 포커스가 컨트롤 중 하나를 대화 상자에서 하는 경우에 0을 반환할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 MFC 대화 상자를 만들 때 (사용 하 여는 [만들기](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), 또는 [DoModal](../../mfc/reference/cdialog-class.md#domodal) 에서 상속 된 [CDialog](../../mfc/reference/cdialog-class.md)), `WM_INITDIALOG` 메시지가 전송 되 고이 메서드를 호출 합니다. 대화 상자에 있는 Windows Forms 컨트롤의 인스턴스를 만들고 하 고 사용자 정의 컨트롤의 크기에 맞게 대화 상자의 크기를 조정 합니다. 그런 다음 MFC 대화 상자에서 새 컨트롤을 호스팅합니다.  
  
 대화 상자 초기화 될 때 특수 한 처리를 수행 하는 경우이 멤버 함수를 재정의 합니다. 이 메서드 사용에 대 한 자세한 내용은 참조 하십시오. [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)합니다.  
  
##  <a name="operator_-_gt"></a>CWinFormsDialog::operator-&gt;  
 대체 [CWinFormsDialog::GetControl](#getcontrol) 식에 있습니다.  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>주의  
 이 연산자를 대체 하는 편리한 구문을 제공 `GetControl` 식에 있습니다.  
  
 Windows Forms에 대 한 정보를 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
##  <a name="operator_tmanagedcontrol_xor"></a>CWinFormsDialog::operator TManagedControl ^  
 Windows Forms 사용자 정의 컨트롤에 대 한 참조로 형식을 캐스팅합니다.  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>주의  
 이 연산자는 Windows Forms 컨트롤에 대 한 참조로 형식을 캐스팅합니다. 전달 하는 데 사용 되는 `CWinFormsDialog<``TManagedControl``>` 대화 상자를 Windows Forms 사용자 컨트롤 개체에 대 한 포인터를 허용 하는 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md)   
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)

