---
title: "CSnapInPropertyPageImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f5db4d0742a423e9574db2a4268a9376491b2ed2
ms.lasthandoff: 02/24/2017

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
|[CSnapInPropertyPageImpl::OnApply](#onapply)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **지금 적용** 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **도움말** 마법사 형식의 속성 시트를 사용 하는 동안 단추.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|현재 페이지의 더 이상 활성 상태가 때 프레임 워크에 의해 호출 됩니다.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **취소** 단추는 취소 작업이 수행 하기 전에 합니다.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|사용자가 클릭할 때 프레임 워크에서 호출의 **재설정** 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|현재 페이지 활성화 되는 프레임 워크에서 호출 합니다.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **다시** 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 **마침** 마법사 형식의 속성 시트를 사용 하는 동안 단추.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|사용자가 클릭할 때 프레임 워크에 의해 호출 된 `Next` 마법사 형식의 속성 시트를 사용 하는 동안 단추입니다.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|속성 시트의 모든 페이지에 있는 현재 메시지를 전달합니다.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|호출을 활성화 또는 비활성화는 **지금 적용** 단추입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows **PROPSHEETPAGE** 에서 사용 하는 구조는 `CSnapInPropertyPageImpl` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `CSnapInPropertyPageImpl`스냅인 속성 페이지 개체에 대 한 기본 구현을 제공합니다. 스냅인 속성 페이지의 기본 기능 몇 가지 다른 인터페이스를 사용 하 여 구현 됩니다 및 형식을 매핑합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsnap.h  
  
##  <a name="a-namecanceltoclosea--csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose  
 모달 속성 시트의 페이지에서 데이터를 복구할 수 없는 변경 되는 수행 된 후이 함수를 호출 합니다.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>주의  
 이 함수는 변경의 **확인** 단추를 **닫기** 사용 하지 않도록 설정 하 고는 **취소** 단추입니다. 이 변경 알림 사용자 변경 내용을 영구적 이며 수정 작업을 취소할 수 없습니다.  
  
 `CancelToClose` 모덜리스 속성 시트에 없기 때문에 멤버 함수는 모덜리스 속성 시트의 경우 nothing을 **취소** 기본적으로는 단추입니다.  
  
##  <a name="a-namecsnapinpropertypageimpla--csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 `CSnapInPropertyPageImpl` 개체를 생성합니다.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTitle`  
 [in] 속성 페이지의 제목입니다.  
  
### <a name="remarks"></a>주의  
 기본 구조를 초기화 하려면 호출 [CSnapInPropertyPageImpl::Create](#create)합니다.  
  
##  <a name="a-namecreatea--csnapinpropertypageimplcreate"></a><a name="create"></a>CSnapInPropertyPageImpl::Create  
 속성 페이지의 기본 구조를 초기화 하려면이 함수를 호출 합니다.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 핸들을 **PROPSHEETPAGE** 새로 만든된 속성 시트의 특성을 포함 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 먼저 호출 해야 [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) 이 함수를 호출 하기 전에 합니다.  
  
##  <a name="a-namempspa--csnapinpropertypageimplmpsp"></a><a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp  
 `m_psp`멤버의 특성을 저장 하는 구조 **PROPSHEETPAGE**합니다.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>주의  
 이 구조를 사용 하 여 생성 한 후 속성 페이지의 모양을 초기화 합니다.  
  
 해당 멤버의 목록을 포함 하 여이 구조에 대 한 자세한 내용은 참조 [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameonapplya--csnapinpropertypageimplonapply"></a><a name="onapply"></a>CSnapInPropertyPageImpl::OnApply  
 이 멤버 함수를 클릭할 때 호출의 **확인** 또는 **지금 적용** 단추입니다.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>반환 값  
 변경 내용을 허용 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 전에 `OnApply` 호출할 수 호출 했어야는 프레임 워크에 의해 `SetModified` 해당 매개 변수를 설정 하 고 **TRUE**합니다. 그러면 활성화 됩니다는 **지금 적용** 속성 페이지에는 사용자가 변경할 즉시 단추입니다.  
  
 프로그램은 사용자가 클릭 동작을 지정 하려면이 멤버 함수 재정의 **지금 적용** 단추입니다. 함수를 재정의할 때 반환 해야 **TRUE** 변경 내용을 적용할 및 **FALSE** 변경 내용이 적용 되지 않게 합니다.  
  
 기본 구현은 `OnApply` 반환 **TRUE**합니다.  
  
##  <a name="a-nameonhelpa--csnapinpropertypageimplonhelp"></a><a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp  
 이 멤버 함수를 클릭할 때 호출의 **도움말** 속성 페이지에 대 한 단추입니다.  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>주의  
 속성 페이지에 대 한 도움말을 표시 하려면이 멤버 함수를 재정의 합니다.  
  
##  <a name="a-nameonkillactivea--csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive  
 이 멤버 함수는 페이지가 더 이상 활성 페이지가 있을 때 호출 됩니다.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>반환 값  
 데이터를 업데이트 했습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 특수 한 데이터 유효성 검사 작업을 수행 하려면이 멤버 함수를 재정의 합니다.  
  
##  <a name="a-nameonquerycancela--csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel  
 이 멤버 함수를 클릭할 때 호출는 **취소** 단추를 취소 하기 전에 작업이 수행 되어 있습니다.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>반환 값  
 취소 작업에서 허용 하는 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 프로그램은 사용자가 클릭 하는 동작을 지정 하려면이 멤버 함수 재정의 **취소** 단추입니다.  
  
 기본 구현은 `OnQueryCancel` 반환 **TRUE**합니다.  
  
##  <a name="a-nameonreseta--csnapinpropertypageimplonreset"></a><a name="onreset"></a>CSnapInPropertyPageImpl::OnReset  
 이 멤버 함수를 클릭할 때 호출의 **취소** 단추입니다.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>주의  
 이 함수를 호출할 때 변경 이전에 클릭 하면 사용자가 만든 모든 속성 페이지에는 **지금 적용** 단추는 무시 되 고 포커스를 유지 하는 속성 시트입니다.  
  
 프로그램은 사용자가 클릭 동작을 지정 하려면이 멤버 함수 재정의 **취소** 단추입니다.  
  
##  <a name="a-nameonsetactivea--csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive  
 이 멤버 함수는 페이지는 사용자가 선택한를 활성 페이지 될 때 호출 됩니다.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>반환 값  
 페이지가 성공적으로 활성화 설정 되었으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 페이지가 활성화 될 때 작업을 수행 하려면이 멤버 함수를 재정의 합니다. 이 멤버 함수 재정의 다른 처리를 수행 하기 전에 기본 버전을 호출 해야 합니다.  
  
 기본 구현에서는 반환 **TRUE**합니다.  
  
##  <a name="a-nameonwizardbacka--csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack  
 이 멤버 함수를 클릭할 때 호출는 **다시** 마법사의 단추입니다.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>반환 값  
  
-   자동으로 이전 페이지로 이동 하는&0;입니다.  
  
-   페이지를 변경 하지 않도록 하려면-1입니다.  
  
 다음 중이 아닌 페이지를 이동, 대화 상자를 표시할 수의 식별자를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 사용자 경우에 수행 해야 하는 몇 가지 동작을 지정 하려면이 멤버 함수 재정의 **다시** 단추를 클릭 합니다.  
  
##  <a name="a-nameonwizardfinisha--csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish  
 이 멤버 함수를 클릭할 때 호출는 **완료** 마법사의 단추입니다.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>반환 값  
 속성 시트는 마법사를 완료 합니다; 손상 된 경우&0;이 아닌 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 사용자 경우에 수행 해야 하는 몇 가지 동작을 지정 하려면이 멤버 함수 재정의 **마침** 단추를 클릭 합니다.  
  
##  <a name="a-nameonwizardnexta--csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext  
 이 멤버 함수를 클릭할 때 호출는 `Next` 마법사의 단추입니다.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>반환 값  
  
-   다음 페이지에 자동으로 이동 하는&0;입니다.  
  
-   페이지를 변경 하지 않도록 하려면-1입니다.  
  
 다음 중이 아닌 페이지를 이동, 대화 상자를 표시할 수의 식별자를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 사용자 경우에 수행 해야 하는 몇 가지 동작을 지정 하려면이 멤버 함수 재정의 `Next` 단추를 클릭 합니다.  
  
##  <a name="a-namequerysiblingsa--csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings  
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
 다음 속성 페이지에 메시지를 전달할 수 해야 하면&0;이 아니고 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 속성 시트는 페이지에서&0;이 아닌 값을 반환 하는 경우 후속 페이지에 메시지를 보내지 않습니다.  
  
##  <a name="a-namesetmodifieda--csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified  
 활성화 또는 비활성화 하려면이 멤버 함수 호출의 **지금 적용** 단추를 적절 한 외부 개체에 속성 페이지에서 설정을 적용 여부에 따라 합니다.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bChanged`  
 [in] **TRUE** 속성 페이지 설정; 적용 된 마지막 시간 이후 수정 된 것을 나타내려면 **FALSE** 되었음을 나타내려면 속성 페이지 설정이 적용 된 무시 해야 합니다.  
  
### <a name="remarks"></a>주의  
 속성 시트 유지 트랙의 페이지는 "더티" 즉, 속성 페이지를 호출한 **SetModified (TRUE)**합니다. **지금 적용** 단추 호출 하는 경우에 항상 사용할 수 **SetModified (TRUE)** 페이지 중 하나에 대 한 합니다. **지금 적용** 를 호출 하면 단추가 비활성화 되며 **SetModified (FALSE)** 만 하는 경우 다른 페이지는 "더티". 하지만 페이지 중 하나에 대 한  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

