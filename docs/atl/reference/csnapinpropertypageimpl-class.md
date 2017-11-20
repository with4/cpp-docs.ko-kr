---
title: "CSnapInPropertyPageImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
dev_langs: C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 230ebd2543a559712d491d5acacdbc1f660b3450
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl 클래스
이 클래스는 스냅인 속성 페이지 개체를 구현 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
CSnapInPropertyPageImpl : public CDialogImplBase
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|상태를 변경 하는 **확인** 및 **취소** 단추입니다.|  
|[CSnapInPropertyPageImpl::Create](#create)|새로 만든 초기화 `CSnapInPropertyPageImpl` 개체입니다.|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|사용자가 클릭할 때 프레임 워크에서 호출 된 **지금 적용** 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|사용자가 클릭할 때 프레임 워크에서 호출 된 **도움말** 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|현재 페이지가 더 이상 활성 상태가 프레임 워크에서 호출 됩니다.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|사용자가 클릭할 때 프레임 워크에서 호출 된 **취소** 단추는 취소 작업이 수행 되기 전에 합니다.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|사용자가 클릭할 때 프레임 워크에서 호출 된 **다시 설정** 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|현재 페이지 활성화 될 때 프레임 워크에서 호출 됩니다.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|사용자가 클릭할 때 프레임 워크에서 호출 된 **다시** 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|사용자가 클릭할 때 프레임 워크에서 호출 된 **마침** 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|사용자가 클릭할 때 프레임 워크에서 호출 된 `Next` 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|속성 시트의 모든 페이지에 현재 메시지를 전달합니다.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|활성화 하거나 비활성화 하는 호출 된 **지금 적용** 단추입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows **PROPSHEETPAGE** 에서 사용 하는 구조는 `CSnapInPropertyPageImpl` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `CSnapInPropertyPageImpl`스냅인 속성 page 개체에 대 한 기본 구현을 제공합니다. 스냅인 속성 페이지의 기본 기능 몇 가지 다른 인터페이스를 사용 하 여 구현 됩니다 및 형식을 매핑합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsnap.h  
  
##  <a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose  
 모달 속성 시트의 페이지의 데이터를 복구할 수 없는 변경 수행 된 후이 함수를 호출 합니다.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>설명  
 이 함수는 변경의 **확인** 단추를 **닫기** 사용 하지 않도록 설정 하 고는 **취소** 단추입니다. 이렇게 하면 변경 알림을 영구적 및 수정 내용을 변경이 하다 사용자를 취소할 수 없습니다.  
  
 `CancelToClose` 모덜리스 속성 시트에 없기 때문에 멤버 함수는 모덜리스 속성 시트의 경우 nothing는 **취소** 기본적으로는 단추입니다.  
  
##  <a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 `CSnapInPropertyPageImpl` 개체를 생성합니다.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTitle`  
 [in] 속성 페이지의 제목입니다.  
  
### <a name="remarks"></a>설명  
 기본 구조를 초기화 하려면 호출 [CSnapInPropertyPageImpl::Create](#create)합니다.  
  
##  <a name="create"></a>CSnapInPropertyPageImpl::Create  
 속성 페이지의 기본 구조를 초기화 하려면이 함수를 호출 합니다.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 핸들을 **PROPSHEETPAGE** 새로 만든된 속성 시트의 특성을 포함 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 먼저 호출 해야 [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) 이 함수를 호출 하기 전에.  
  
##  <a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp  
 `m_psp`멤버의 특성을 저장 하는 구조 **PROPSHEETPAGE**합니다.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>설명  
 이 구조를 사용 하 여 생성 한 후 속성 페이지의 모양을 초기화 합니다.  
  
 해당 멤버의 목록을 포함 하 여이 구조에 대 한 자세한 내용은 참조 [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) Windows sdk에서입니다.  
  
##  <a name="onapply"></a>CSnapInPropertyPageImpl::OnApply  
 이 멤버 함수는 사용자가 클릭할 때 호출 됩니다는 **확인** 또는 **지금 적용** 단추입니다.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>반환 값  
 변경 내용을 허용 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 하기 전에 `OnApply` 호출할 수는 프레임 워크에서 호출 해야 `SetModified` 해당 매개 변수를 설정 하 고 **TRUE**합니다. 그러면 활성화 됩니다는 **지금 적용** 속성 페이지에서 사용자가을 변경 하는 즉시 단추입니다.  
  
 프로그램은 사용자가 클릭 동작을 지정 하려면이 멤버 함수 재정의 **지금 적용** 단추입니다. 함수를 재정의할 때 반환 해야 **TRUE** 변경 내용을 적용할 수 및 **FALSE** 변경 내용이 적용 되지 않게 하려면.  
  
 기본 구현은 `OnApply` 반환 **TRUE**합니다.  
  
##  <a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp  
 이 멤버 함수는 사용자가 클릭할 때 호출 됩니다는 **도움말** 속성 페이지에 대 한 단추입니다.  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>설명  
 속성 페이지에 대 한 도움말을 표시 하려면이 멤버 함수를 재정의 합니다.  
  
##  <a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive  
 이 멤버 함수는 페이지가 더 이상 활성 페이지가 있을 때 호출 됩니다.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>반환 값  
 데이터를 성공적으로 업데이트 한 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 특별 한 데이터 유효성 검사 작업을 수행 하려면이 멤버 함수를 재정의 합니다.  
  
##  <a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel  
 이 멤버 함수는 사용자가 클릭할 때 호출 됩니다는 **취소** 단추를 취소 하기 전에 작업이 수행 되어 있습니다.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>반환 값  
 취소 작업이; 허용 하려면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 재정의 하는 프로그램은 사용자가 클릭 한 작업을 지정 하려면이 함수는 **취소** 단추입니다.  
  
 기본 구현은 `OnQueryCancel` 반환 **TRUE**합니다.  
  
##  <a name="onreset"></a>CSnapInPropertyPageImpl::OnReset  
 이 멤버 함수는 사용자가 클릭할 때 호출 됩니다는 **취소** 단추입니다.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>설명  
 이 함수를 호출할 때 변경 이전에 클릭 하면 사용자가 만든 모든 속성 페이지에는 **지금 적용** 단추는 무시 되 고 속성 시트 포커스를 유지 합니다.  
  
 재정의 하는 프로그램은 사용자가 클릭 동작을 지정 하려면이 함수는 **취소** 단추입니다.  
  
##  <a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive  
 이 멤버 함수는 페이지는 사용자가 선택 되 고 활성 페이지가 됩니다 때 호출 됩니다.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>반환 값  
 페이지를 성공적으로 활성화를 설정한 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 페이지가 활성화 될 때 작업을 수행 하려면이 멤버 함수를 재정의 합니다. 이 멤버 함수 재정의 다른 처리를 수행 하기 전에 기본 버전을 호출 해야 합니다.  
  
 기본 구현은 반환 **TRUE**합니다.  
  
##  <a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack  
 이 멤버 함수는 사용자가 클릭할 때 호출 됩니다는 **다시** 는 마법사에서 단추입니다.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>반환 값  
  
-   자동으로 이전 페이지로 이동 하는 0입니다.  
  
-   변경할 수 없도록 하려면 페이지-1입니다.  
  
 다음 중이 아닌 페이지를 이동 하려면 대화 상자를 표시할 수의 식별자를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 재정의 될 때 수행 되어야 하는 몇 가지 동작을 지정 하려면이 함수는 **다시** 단추를 클릭 합니다.  
  
##  <a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish  
 이 멤버 함수는 사용자가 클릭할 때 호출 됩니다는 **마침** 는 마법사에서 단추입니다.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>반환 값  
 마법사를 완료 합니다; 속성 시트 손상 된 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 재정의 될 때 수행 되어야 하는 몇 가지 동작을 지정 하려면이 함수는 **마침** 단추를 클릭 합니다.  
  
##  <a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext  
 이 멤버 함수는 사용자가 클릭할 때 호출 됩니다는 `Next` 는 마법사에서 단추입니다.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>반환 값  
  
-   다음 페이지를 자동으로 이동 하는 0입니다.  
  
-   변경할 수 없도록 하려면 페이지-1입니다.  
  
 다음 중이 아닌 페이지를 이동 하려면 대화 상자를 표시할 수의 식별자를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 재정의 될 때 수행 되어야 하는 몇 가지 동작을 지정 하려면이 함수는 `Next` 단추를 클릭 합니다.  
  
##  <a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings  
 속성 시트의 각 페이지에 메시지를 전달 하려면이 멤버 함수를 호출 합니다.  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `wParam`  
 [in] 추가 메시지 종속 정보를 지정 합니다.  
  
 `lParam`  
 [in] 추가 메시지 종속 정보를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 다음 속성 페이지로; 메시지가 전달 되지 않아야 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 속성 시트는 0이 아닌 값을 반환 하는 페이지의 후속 페이지에 메시지를 보내지 않습니다.  
  
##  <a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified  
 사용 하지 않도록 설정 하거나 설정 하려면이 함수를 호출는 **지금 적용** 적절 한 외부 개체의 속성 페이지에서 설정을 적용 여부에 따라 단추입니다.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bChanged`  
 [in] **TRUE** 속성 페이지 설정; 적용 된 마지막 시간 이후 수정 된 것을 나타내기 위해 **FALSE** 속성 페이지 설정을 적용 하지 또는 무시할지를 나타내는입니다.  
  
### <a name="remarks"></a>설명  
 속성 시트 유지 트랙의 페이지는 "더티" 즉, 속성 페이지를 호출한 **SetModified (TRUE)**합니다. **지금 적용** 호출 하는 경우 단추가 활성화 되어 항상 **SetModified (TRUE)** 페이지 중 하나에 대 한 합니다. **지금 적용** 호출 하는 경우 단추가 비활성화 됩니다 **SetModified (FALSE)** 만 하는 경우 다른 페이지는 "더티"입니다. 하지만 페이지 중 하나에 대 한  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
