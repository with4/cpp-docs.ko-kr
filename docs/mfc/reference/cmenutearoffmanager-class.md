---
title: CMenuTearOffManager 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
dev_langs:
- C++
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dcbd5ea33b50e66d1c9e858669a3174042a19e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367671"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager 클래스
분리 메뉴를 관리합니다. 분리 메뉴는 메뉴 모음의 메뉴입니다. 사용자는 메뉴 모음에서 분리 메뉴를 제거하여 이동 가능한 상태로 만들 수 있습니다.  
  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>구문  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|`CMenuTearOffManager` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMenuTearOffManager::Build](#build)||  
|[CMenuTearOffManager::GetRegPath](#getregpath)||  
|[CMenuTearOffManager::Initialize](#initialize)|초기화 한 `CMenuTearOffManager` 개체입니다.|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>설명  
 응용 프로그램에서 분리 메뉴를 사용 하려면 있어야는 `CMenuTearOffManager` 개체입니다. 대부분의 경우에서 만들기 또는 초기화 하지 않습니다는 `CMenuTearOffManager` 개체를 직접 합니다. 이 자동으로 처리를 호출할 때는 [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) 함수입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 하 고 초기화 하는 `CMenuTearOffManager` 호출 하 여 개체는 `CWinAppEX::EnableTearOffMenus` 메서드. 이 코드 조각은 [워드 패드 샘플](../../visual-cpp-samples.md)의 일부입니다.  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmenutearoffmanager.h  
  
##  <a name="build"></a>  CMenuTearOffManager::Build  

  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiTearOffBarID`  
 [in] `strText`  
  
### <a name="remarks"></a>설명  
  
##  <a name="cmenutearoffmanager"></a>  CMenuTearOffManager::CMenuTearOffManager  
 생성 된 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 개체입니다.  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>설명  
 대부분의 경우에서 만들지 마십시오는 `CMenuTearOffManager` 수동으로 합니다. 응용 프로그램의 프레임 워크 만듭니다는 `CMenuTearOffManager` 호출 하는 경우 개체 [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)합니다.  
  
##  <a name="getregpath"></a>  CMenuTearOffManager::GetRegPath  

  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="initialize"></a>  CMenuTearOffManager::Initialize  
 초기화는 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 개체입니다.  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszRegEntry`  
 레지스트리 항목의 경로 포함 하는 문자열입니다. 응용 프로그램에서이 레지스트리 항목 분리 막대에 대 한 설정을 저장 합니다.  
  
 [in] `uiTearOffMenuFirst`  
 분리 메뉴에 대 한 첫 번째 메뉴 ID를 지정 합니다.  
  
 [in] `uiTearOffMenuLast`  
 분리 메뉴에 대 한 마지막 메뉴 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 메뉴 Id의 범위 `uiTearOffMenuFirst` 를 `uiTearOffMenuLast` 연속 간격 이어야 합니다. 간격의 응용 프로그램에 동시에 나타날 수 있는 분리 메뉴를 정의 합니다.  
  
##  <a name="isdynamicid"></a>  CMenuTearOffManager::IsDynamicID  

  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="parse"></a>  CMenuTearOffManager::Parse  

  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `str`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="reset"></a>  CMenuTearOffManager::Reset  

  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hmenu`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setinuse"></a>  CMenuTearOffManager::SetInUse  

  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdId`  
 [in] `bUse`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setuptearoffmenus"></a>  CMenuTearOffManager::SetupTearOffMenus  

  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hMenu`  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
