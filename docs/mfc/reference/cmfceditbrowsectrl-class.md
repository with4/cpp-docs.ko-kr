---
title: "CMFCEditBrowseCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCEditBrowseCtrl::PreTranslateMessage method
- CMFCEditBrowseCtrl constructor
- CMFCEditBrowseCtrl class
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: 33
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5c5650da677a442628049c9ef4b41c2142cfb2c2
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl 클래스
`CMFCEditBrowseCtrl` 클래스는 필요에 따라 찾아보기 단추를 포함 하는 편집 가능한 텍스트 상자 인 편집 찾아보기 컨트롤을 지원 합니다. 사용자가 찾아보기 단추를 클릭하면 컨트롤은 사용자 지정 작업을 수행하거나 파일 브라우저 또는 폴더 브라우저가 포함된 표준 대화 상자를 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|기본 생성자입니다.|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|(숨깁니다)를 사용 하지 않도록 설정 하거나 찾아보기 단추입니다.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|찾아보기 단추를 활성화 하 고 편집 찾아보기 컨트롤에 배치 *파일 찾아보기* 모드입니다.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|찾아보기 단추를 활성화 하 고 편집 찾아보기 컨트롤에 배치 *폴더 찾아보기* 모드입니다.|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|현재 찾아보기 모드를 반환합니다.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|편집 찾아보기 컨트롤 찾아보기 동작의 결과 함께 업데이트 되는 프레임 워크에서 호출 합니다.|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|사용자가 찾아보기 단추를 클릭 한 후에 프레임 워크에서 호출 합니다.|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|현재 편집 찾아보기 컨트롤을 다시 그립니다.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|찾아보기 단추를 그릴 프레임 워크에 의해 호출 됩니다.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|편집 컨트롤에 잘못 된 파일 이름을 입력 한 때 프레임 워크에 의해 호출 됩니다.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|창 메시지를 변환 하 여으로 디스패치 되기 전에 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다. 구문 및 자세한 정보에 대 한 참조 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)합니다.|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|찾아보기 단추에 대 한 사용자 지정 이미지를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 편집 찾아보기 컨트롤을 사용 하 여 파일 또는 폴더 이름을 선택 합니다. 필요에 따라 대화 상자를 표시와 같은 사용자 지정 작업을 수행 하도록 컨트롤을 사용 합니다. 표시 하거나 찾아보기 단추를 표시 하지 수 있으며 단추에 사용자 지정 레이블 또는 이미지를 적용할 수 있습니다.  
  
 *찾아보기 모드* 편집 찾아보기 컨트롤을 결정 합니다 찾아보기 단추를 표시 하는지 여부와 어떤 작업 단추를 클릭할 때 발생 합니다. 자세한 내용은 참조는 [GetMode](#getmode) 메서드.  
  
 `CMFCEditBrowseCtrl` 클래스에서는 다음 모드를 지원 합니다.  
  
 `custom mode`  
 사용자 지정 작업에는 찾아보기 단추를 클릭할 때 수행 됩니다. 예를 들어 응용 프로그램 관련 대화 상자를 표시할 수 있습니다.  
  
 `file mode`  
 찾아보기 단추를 클릭할 때 표준 파일 선택 대화 상자가 표시 됩니다.  
  
 `folder mode`  
 표준 폴더 선택 대화 상자에서 찾아보기 단추를 클릭할 때 표시 됩니다.  
  
## <a name="how-to-specify-an-edit-browse-control"></a>방법: 편집 찾아보기 컨트롤 지정  
 응용 프로그램에서 편집 찾아보기 컨트롤을 통합 하려면 다음 단계를 수행 합니다.  
  
1.  사용자 지정 찾아보기 모드를 구현 하려면 파생 클래스에서 사용자 지정은 `CMFCEditBrowseCtrl` 클래스 한 후 재정의 [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) 메서드. 재정의 메서드에서 사용자 지정 찾아보기 동작을 실행 하 고 결과와 편집 찾아보기 컨트롤을 업데이트 합니다.  
  
2.  포함 하거나는 `CMFCEditBrowseCtrl` 개체 또는 부모 창 개체로 파생된 편집 찾아보기 컨트롤 개체입니다.  
  
3.  사용 하는 경우는 **클래스 마법사** 대화 상자를 만들려면 추가 편집 컨트롤 ( `CEdit`) 대화 상자 폼을 합니다. 또한 헤더 파일에서 컨트롤에 액세스 하는 변수를 추가 합니다. 헤더 파일에서에서 변수 유형을 변경 `CEdit` 를 `CMFCEditBrowseCtrl`합니다. 편집 찾아보기 컨트롤을 자동으로 생성 됩니다. 사용 하지 않는 경우는 **클래스 마법사**, 추가 `CMFCEditBrowseCtrl` 헤더 파일을 호출한 다음 변수는 `Create` 메서드.  
  
4.  사용 하 여 대화 상자에는 편집 찾아보기 컨트롤을 추가 하는 경우는 **ClassWizard** 데이터 교환을 설정 하는 도구입니다.  
  
5.  호출의 [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), 또는 [EnableBrowseButton](#enablebrowsebutton) 메서드 찾아보기 모드를 설정 하 고 찾아보기 단추를 표시 합니다. 호출의 [GetMode](#getmode) 메서드는 현재 찾아보기 모드를 얻으려고 합니다.  
  
6.  찾아보기 단추를 사용자 지정 이미지를 제공 하려면 호출의 [SetBrowseButtonImage](#setbrowsebuttonimage) 메서드나 재정의 [OnDrawBrowseButton](#ondrawbrowsebutton) 메서드.  
  
7.  에서 제거 하려면 찾아보기 단추 편집 찾아보기 컨트롤을 호출 하는 [EnableBrowseButton](#enablebrowsebutton) 메서드는 `bEnable` 매개 변수 설정 `FALSE`합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>예제  
 다음 예제에서 두 개의 메서드를 사용 하는 방법을 보여 줍니다는 `CMFCEditBrowseCtrl` 클래스: `EnableFolderBrowseButton` 및 `EnableFileBrowseButton`합니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls #&6;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&7;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxeditbrowsectrl.h  
  
##  <a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton  
 표시 하거나 찾아보기 단추를 현재 편집 찾아보기 컨트롤에 표시 되지 않습니다.  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>매개 변수  
 `bEnable`  
 `TRUE`찾아보기 단추;를 표시 하려면 `FALSE` 를 찾아보기 단추를 표시 하지 않습니다. 기본값은 `TRUE`입니다.  
  
 `szLabel`  
 찾아보기 단추에 표시 되는 레이블. 기본값은 " **... **".  
  
### <a name="remarks"></a>주의  
 하는 경우는 `bEnable` 매개 변수는 `TRUE`, 찾아보기 단추를 클릭할 때 수행할 사용자 지정 작업을 구현 합니다. 사용자 지정 작업을 구현 하려면에서 클래스를 파생 된 `CMFCEditBrowseCtrl` 클래스를 재정의 한 다음 해당 [OnBrowse](#onbrowse) 메서드.  
  
 하는 경우는 `bEnable` 매개 변수는 `TRUE`, 컨트롤의 찾아보기 모드 `BrowseMode_Default`고, 그렇지 않으면 찾아보기 모드 `BrowseMode_None`합니다. 찾아보기 모드에 대 한 자세한 내용은 참조는 [GetMode](#getmode) 메서드.  
  
##  <a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton  
 현재 편집 찾아보기 컨트롤에 있는 찾아보기 단추를 표시 하 고에 컨트롤 배치 *파일 찾아보기* 모드입니다.  
  
```  
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,  
    LPCTSTR lpszFilter=NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszDefExt`  
 파일 선택 대화 상자에서 사용되는 기본 파일 이름 확장명을 지정합니다. 기본값은 `NULL`입니다.  
  
 `lpszFilter`  
 파일 선택 대화 상자에서 사용되는 기본 필터 문자열을 지정합니다. 기본값은 `NULL`입니다.  
  
 `dwFlags`  
 대화 상자 플래그입니다. 기본값은 OFN_HIDEREADONLY와 OFN_OVERWRITEPROMPT의 비트 조합(OR)입니다.  
  
### <a name="remarks"></a>주의  
 편집 찾아보기 컨트롤이 파일 찾아보기 모드에 있고 사용자가 찾아보기 단추를 클릭하는 경우 컨트롤이 표준 파일 선택 대화 상자를 표시합니다.  
  
 사용 가능한 플래그의 전체 목록은 참조 하십시오. [OPENFILENAME 구조](https://msdn.microsoft.com/library/ms646839.aspx)합니다.  
  
##  <a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 현재 편집 찾아보기 컨트롤에 있는 찾아보기 단추를 표시 하 고에 컨트롤 배치 *폴더 찾아보기* 모드입니다.  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>주의  
 폴더 찾아보기 모드에서 편집 찾아보기 컨트롤은 사용자가 찾아보기 단추를 클릭 하는 경우 컨트롤 표준 폴더 선택 대화 상자를 표시 합니다.  
  
##  <a name="getmode"></a>CMFCEditBrowseCtrl::GetMode  
 찾아보기 모드의 현재 편집 찾아보기 컨트롤을 검색합니다.  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 편집 모드를 지정 하는 열거형 값 중 하나 컨트롤을 이동 합니다. 찾아보기 모드는 프레임 워크에서 찾아보기 단추를 표시 하는 여부와 해당 단추를 클릭할 때를 결정 합니다.  
  
 다음 표에서는 가능한 반환 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode`. 프로그래머 정의 동작이 수행 됩니다.|  
|`BrowseMode_File`|`file mode`. 표준 파일 브라우저 대화 상자가 표시 됩니다.|  
|`BrowseMode_Folder`|`folder mode`. 표준 폴더 브라우저 대화 상자가 표시 됩니다.|  
|`BrowseMode_None`|찾아보기 단추는 표시 되지 않습니다.|  
  
### <a name="remarks"></a>주의  
 기본적으로는 `CMFCEditBrowseCtrl` 개체도 초기화 됩니다 `BrowseMode_None` 모드입니다. 사용 하 여 찾아보기 모드를 수정 된 [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), 및 [CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton) 메서드.  
  
##  <a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate  
 편집 찾아보기 컨트롤 찾아보기 동작의 결과 함께 업데이트 되는 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>주의  
 사용자 지정 동작을 구현 하려면 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse  
 사용자가 편집 찾아보기 컨트롤의 찾아보기 단추를 클릭 한 후에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 편집 찾아보기 컨트롤의 찾아보기 단추를 클릭할 때 사용자 지정 코드를 실행 합니다. 고유한 클래스를 파생 시키는 `CMFCEditBrowseCtrl` 클래스 다이어그램과 해당 `OnBrowse` 메서드. 해당 메서드에 사용자 지정 찾아보기 동작을 구현 하 고 필요에 따라 편집 찾아보기 컨트롤의 텍스트 상자를 업데이트 합니다. 응용 프로그램에서 사용 하 여는 [EnableBrowseButton](#enablebrowsebutton) 편집 찾아보기 컨트롤 입력 하기 위한 방법은 *사용자 지정 찾아보기* 모드입니다.  
  
##  <a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout  
 현재 편집 찾아보기 컨트롤을 다시 그립니다.  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>주의  
 프레임 워크는 찾아보기 모드 편집 찾아보기의 변경 내용을 제어 하는 경우이 메서드를 호출 합니다. 자세한 내용은 참조 [CMFCEditBrowseCtrl::GetMode](#getmode)합니다.  
  
##  <a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton  
 편집 찾아보기 컨트롤에 있는 찾아보기 단추를 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsButtonPressed,  
    BOOL bIsButtonHot);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 `Rect`  
 찾아보기 단추의 경계 사각형입니다.  
  
 `bIsButtonPressed`  
 `TRUE`단추를 누르면 됩니다. 그렇지 않으면 `FALSE`합니다.  
  
 `bIsButtonHot`  
 `TRUE`단추가; 강조 표시 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 찾아보기 단추 모양 사용자 지정 하려면 파생된 클래스에서이 함수를 재정의 합니다.  
  
##  <a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage  
 편집 찾아보기 컨트롤의 찾아보기 단추를 사용자 지정 이미지를 설정합니다.  
  
```  
void SetBrowseButtonImage(
    HICON hIcon,  
    BOOL bAutoDestroy= TRUE);

 
void SetBrowseButtonImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy= TRUE);  
  
void SetBrowseButtonImage(UINT uiBmpResId);
```  
  
### <a name="parameters"></a>매개 변수  
 `hIcon`  
 아이콘의 핸들입니다.  
  
 `hBitmap`  
 비트맵의 핸들입니다.  
  
 `uiBmpResId`  
 비트맵의 리소스 ID입니다.  
  
 `bAutoDestroy`  
 `TRUE`이 메서드가 종료 되 고 때 지정 된 아이콘 또는 비트맵을 삭제 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
 찾아보기 단추를 사용자 지정 이미지를 적용 하려면이 메서드를 사용 합니다. 기본적으로 프레임 워크 가져옵니다 표준 이미지 편집 찾아보기 컨트롤에 때 *파일 찾아보기* 또는 *폴더 찾아보기* 모드입니다.  
  
##  <a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName  
 편집 컨트롤에 잘못 된 파일 이름을 입력 한 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>매개 변수  
 `strFileName`  
 잘못 된 파일 이름을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 해야 `FALSE` 경우 파일 대화 상자에서 보기 위해이 파일 이름을 전달할 수 없습니다. 이 경우 편집 컨트롤에 포커스를 다시 설정 하 고 사용자 계속 편집 해야 합니다. 기본 구현에서는 잘못 된 파일 이름에 대 한이 알리는 메시지 상자를 표시 하 고 반환 `FALSE`합니다. 이 메서드를 재정의 파일 이름을 수정 및 반환 `TRUE` 추가 처리를 위해.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

