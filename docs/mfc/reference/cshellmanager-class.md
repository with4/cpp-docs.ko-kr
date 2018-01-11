---
title: "CShellManager 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
dev_langs: C++
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e1e3fcff06b2937df8218ce1ab32b91ddf22a7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cshellmanager-class"></a>CShellManager 클래스
PIDL(식별자 포인터 목록)에 대한 포인터를 사용하여 작업할 수 있는 몇 가지 메서드를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|`CShellManager` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|셸 폴더를 선택할 수 있도록 해 주는 대화 상자를 표시 합니다.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|두 개의 Pidl를 연결합니다.|  
|[CShellManager::CopyItem](#copyitem)|새 PIDL 만들고 제공 된 PIDL 복사 합니다.|  
|[CShellManager::CreateItem](#createitem)|지정된 된 크기의 새 PIDL를 만듭니다.|  
|[CShellManager::FreeItem](#freeitem)|제공 된 PIDL를 삭제합니다.|  
|[CShellManager::GetItemCount](#getitemcount)|제공 된 PIDL의 항목 수를 반환합니다.|  
|[CShellManager::GetItemSize](#getitemsize)|제공 된 PIDL의 크기를 반환 합니다.|  
|[CShellManager::GetNextItem](#getnextitem)|PIDL에서 다음 항목을 반환합니다.|  
|[CShellManager::GetParentItem](#getparentitem)|제공 된 항목의 부모 항목을 검색합니다.|  
|[CShellManager::ItemFromPath](#itemfrompath)|제공 된 경로 의해 식별 되는 항목에 대 한 PIDL를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 메서드는 `CShellManager` Pidl 처리 하도록 모든 클래스입니다. PIDL은 셸 개체에 대 한 고유 식별자입니다.  
  
 만들지 마십시오는 `CShellManager` 수동으로 개체입니다. 응용 프로그램의 프레임 워크에서 자동으로 생성 될 됩니다. 하지만 호출 해야 [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) 응용 프로그램의 초기화 프로세스 동안 합니다. 응용 프로그램에 대 한 셸 관리자에 대 한 포인터를 가져오려면, 호출 [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>CShellManager::BrowseForFolder  
 셸 폴더를 선택할 수 있도록 해 주는 대화 상자를 표시 합니다.  
  
```  
BOOL BrowseForFolder(
    CString& strOutFolder,  
    CWnd* pWndParent = NULL,  
    LPCTSTR lplszInitialFolder = NULL,  
    LPCTSTR lpszTitle = NULL,  
    UINT ulFlags = BIF_RETURNONLYFSDIRS,  
    LPINT piFolderImage = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `strOutFolder`  
 선택한 폴더의 경로를 저장할 메서드에서 사용 하는 문자열입니다.  
  
 [in] `pWndParent`  
 부모 창에 대 한 포인터입니다.  
  
 [in] `lplszInitialFolder`  
 대화 상자가 표시 되 면 기본적으로 선택 된 폴더를 포함 하는 문자열입니다.  
  
 [in] `lpszTitle`  
 대화 상자에 대 한 제목입니다.  
  
 [in] `ulFlags`  
 대화 상자에 대 한 옵션을 지정 하는 플래그입니다. 참조 [BROWSEINFO](http://msdn.microsoft.com/library/windows/desktop/bb773205) 에 대 한 자세한 내용은 합니다.  
  
 [out] `piFolderImage`  
 메서드가 선택된 된 폴더의 이미지 인덱스를 기록 하는 위치는 정수 값에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 사용자가; 대화 상자에서 폴더를 선택 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출할 때 응용 프로그램 만들고 폴더를 선택할 수 있는 대화 상자를 표시 합니다. 메서드를 폴더의 경로 기록 합니다는 `strOutFolder` 매개 변수입니다.  
  
### <a name="example"></a>예  
 다음 예제에 대 한 참조를 검색 하는 방법을 보여 줍니다는 `CShellManager` 사용 하 여 개체는 `CWinAppEx::GetShellManager` 메서드 및 사용 방법에는 `BrowseForFolder` 메서드. 이 코드 조각은의 일부인는 [탐색기 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>CShellManager::ConcatenateItem  
 두 개의 Pidl 포함 된 새 목록을 만듭니다.  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pidl1`  
 첫 번째 항목입니다.  
  
 [in] `pidl2`  
 두 번째 항목입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 함수가 성공 하면 새 항목 목록에 대 한 포인터 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 만드는 새 [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) 모두 포함 될 수 있을 만큼 큰 `pidl1` 및 `pidl2`합니다. 그런 다음 복사 `pidl1` 및 `pidl2` 새 목록에 있습니다.  
  
##  <a name="copyitem"></a>CShellManager::CopyItem  
 항목 목록에 복사합니다.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pidlSource`  
 원래 항목 목록입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 새로 만든된 항목 목록에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 새로 만든된 항목 목록에는 동일한 크기의 원본 항목 목록에 있습니다.  
  
##  <a name="createitem"></a>CShellManager::CreateItem  
 새 PIDL를 만듭니다.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `cbSize`  
 항목 목록의 크기입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우 만든된 항목 목록에 대 한 포인터 그렇지 않으면 `NULL`합니다.  
  
##  <a name="cshellmanager"></a>CShellManager::CShellManager  
 `CShellManager` 개체를 생성합니다.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>설명  
 대부분의 경우에서 않아도 만들려는 `CShellManager` 직접 합니다. 프레임 워크는 기본적으로 구독을 하나 만듭니다. 에 포인터를 얻으려면는 `CShellManager`, 호출 [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)합니다. 만들면는 `CShellManager` 수동으로 방법으로 초기화 해야 [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)합니다.  
  
##  <a name="freeitem"></a>CShellManager::FreeItem  
 항목 목록을 삭제합니다.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pidl`  
 삭제 하는 항목 목록입니다.  
  
##  <a name="getitemcount"></a>CShellManager::GetItemCount  
 항목 목록에서 항목의 수를 반환합니다.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pidl`  
 항목 목록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 항목 목록에 있는 항목의 수입니다.  
  
##  <a name="getitemsize"></a>CShellManager::GetItemSize  
 항목 목록의 크기를 반환합니다.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pidl`  
 항목 목록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 항목 목록의 크기입니다.  
  
##  <a name="getnextitem"></a>CShellManager::GetNextItem  
 항목 식별자 목록 (PIDL)에 대 한 포인터에서 다음 항목을 검색합니다.  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pidl`  
 반복할 항목의 목록입니다.  
  
### <a name="return-value"></a>반환 값  
 목록에서 다음 항목에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 반환 하는 경우 더 많은 항목이 없는 목록에서 `NULL`합니다.  
  
##  <a name="getparentitem"></a>CShellManager::GetParentItem  
 항목 식별자 목록 (PIDL)에 대 한 포인터의 부모를 검색 합니다.  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpidl`  
 부모가 검색할 PIDL 합니다.  
  
 [out] `lpidlParent`  
 메서드 결과 저장 하는 PIDL에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 PIDL 부모 수준입니다.  
  
### <a name="remarks"></a>설명  
 PIDL 수준은 바탕 화면을 기준으로 합니다. 데스크톱 PIDL 0 수준으로 간주 됩니다.  
  
##  <a name="itemfrompath"></a>CShellManager::ItemFromPath  
 문자열 경로 의해 식별 되는 항목에서 항목 식별자 목록 (PIDL)에 포인터를 검색 합니다.  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszPath`  
 항목에 대 한 경로 지정 하는 문자열입니다.  
  
 [out] `pidl`  
 PIDL에 대 한 참조입니다. 메서드 반환 값에 대 한 포인터를 저장 하려면이 PIDL를 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `NOERROR` 성공 하면 오류 OLE 정의 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)
