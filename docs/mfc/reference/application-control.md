---
title: "응용 프로그램 제어 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- application control
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 81eb0bcdd8c9d154f62635e7f306cefcf7a15c1b
ms.lasthandoff: 02/24/2017

---
# <a name="application-control"></a>응용 프로그램 컨트롤
OLE 응용 프로그램 및 해당 개체에 대 한 상당한 제어가 필요합니다. OLE 시스템 Dll을 시작한 다음 및 응용 프로그램을 자동으로 해제, 개체의 수정 사항과 프로덕션 조정 등 수 있어야 합니다. 이 항목의 함수에는 이러한 요구 사항을 충족 합니다. OLE 시스템 Dll에서 호출 되는 것 외에도 이러한 함수를 때로는 응용 프로그램에서 호출 해야 합니다.  
  
### <a name="application-control"></a>응용 프로그램 컨트롤  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|응용 프로그램이 종료될 수 있는지 여부를 나타냅니다.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|응용 프로그램의 현재 메시지 필터를 검색합니다.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|현재 사용자 컨트롤 플래그를 검색합니다.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|설정 하거나 사용자 정의 컨트롤 플래그를 지웁니다.|  
|[AfxOleLockApp](#afxolelockapp)|응용 프로그램의 활성 개체 수의 프레임 워크의 전역 카운트를 증가 시킵니다.|  
|[AfxOleUnlockApp](#afxoleunlockapp)|감소 프레임 워크의 수가 응용 프로그램의 활성 개체 수입니다.|  
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE 시스템 레지스트리에 있는 서버를 등록합니다.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|에 대 한 사용자 인터페이스를 구현 하는 *typename* 명령 개체입니다.|  
  
##  <a name="a-nameafxolecanexitappa--afxolecanexitapp"></a><a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 응용 프로그램이 종료될 수 있는지 여부를 나타냅니다.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>반환 값  
 응용 프로그램이 종료될 수 있으면 0이 아닌 값이고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 개체에 대해 해결되지 않은 참조가 있으면 응용 프로그램이 종료될 수 없습니다. 전역 함수 `AfxOleLockApp` 및 `AfxOleUnlockApp`은 각각 응용 프로그램의 개체에 대한 참조 수를 늘리거나 줄입니다. 이 카운터가&0;이 아니면 응용 프로그램이 종료될 수 없습니다. 카운터가&0;이 아니면 사용자가 시스템 메뉴에서 닫기를 선택하거나 파일 메뉴에서 종료를 선택할 때 응용 프로그램의 기본 창이 숨겨집니다(제거되지 않음). 이 함수를 호출 하는 프레임 워크 **cframewnd:: Onclose**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAutomation #&2;](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h 

##  <a name="a-nameafxolegetmessagefiltera--afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 응용 프로그램의 현재 메시지 필터를 검색합니다.  
  
```   
COleMessageFilter* AFXAPI  AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>반환 값  
 현재 메시지 필터에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 현재에 액세스 하려면이 함수를 호출 `COleMessageFilter`-파생 개체를 호출 하는 것 처럼 `AfxGetApp` 현재 응용 프로그램 개체에 액세스할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAutomation #&3;](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation #&4;](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxwin.h 

##  <a name="a-nameafxolegetuserctrla--afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 현재 사용자 컨트롤 플래그를 검색합니다.  
  
```   
BOOL  AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>반환 값  
 사용자가 응용 프로그램을 제어 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용자가 사용자가 명시적으로 열거나 새 문서를 만들 때 응용 프로그램의 제어 합니다. 해당 사용자가 컨트롤에는 응용 프로그램이 OLE 시스템 Dll에서 시작 되지 경우-즉, 사용자 시스템 셸 사용 하 여 응용 프로그램을 시작 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h

##  <a name="a-nameafxolesetuserctrla--afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 설정 하거나 해제에 대 한 참조에서 설명 하는 사용자 정의 컨트롤 플래그 `AfxOleGetUserCtrl`합니다.  
  
```  
void  AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>매개 변수  
 *bUserCtrl*  
 사용자 제어 플래그가 설정 되거나 선택이 취소 될 지 여부를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크가이 함수를 호출 하지만 사용자가 만들거나 문서를 로드 하는 경우 문서 로드 하거나 컨테이너 응용 프로그램에서 포함된 된 개체를 로드 하는 등의 간접 작업을 통해 만들 때에 없습니다.  
  
 응용 프로그램의 다른 작업은 응용 프로그램의 제어에 사용자를 입력 해야 하는 경우이 함수를 호출 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h

##  <a name="a-nameafxolelockappa--afxolelockapp"></a><a name="afxolelockapp"></a>AfxOleLockApp  
 응용 프로그램의 활성 개체 수의 프레임 워크의 전역 카운트를 증가 시킵니다.  
  
```   
void  AFXAPI  AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>주의  
 프레임 워크 응용 프로그램에서 활성 개체 수의 개수를 유지 합니다. `AfxOleLockApp` 및 `AfxOleUnlockApp` 함수는 각각 증가 및이 카운트를 감소 시킵니다.  
  
 사용자가 활성 개체를 가진 응용 프로그램을 닫을 하려고 할 때-활성 개체 수는&0;이 아닌 응용 프로그램-프레임 워크는 완전히 종료 되지 않고 사용자의 보기에서 응용 프로그램을 숨깁니다. `AfxOleCanExitApp` 함수는 응용 프로그램이 종료 될 수 있는지 여부를 나타냅니다.  
  
 호출 `AfxOleLockApp` 에서 클라이언트 응용 프로그램에서 사용 되는 동안 소멸 되도록 해당 개체에 적합 하지 않을 수는 경우 OLE 인터페이스를 노출 하는 개체입니다. 또한 호출 `AfxOleUnlockApp` 호출 하는 모든 개체의 소멸자에서 `AfxOleLockApp` 생성자에 있습니다. 기본적으로 `COleDocument` (및 파생 클래스) 자동으로 잠그고 응용 프로그램을 잠금 해제 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAutomation #&5;](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h

##  <a name="a-nameafxoleunlockappa--afxoleunlockapp"></a><a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 감소 프레임 워크의 응용 프로그램에서 활성 개체 수입니다.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>주의  
 참조 `AfxOleLockApp` 자세한 정보.  
  
 활성 개체 수가&0;에 도달 하는 경우 **AfxOleOnReleaseAllObjects** 호출 됩니다.  
  
### <a name="example"></a>예제  
 예를 참조 [AfxOleLockApp](#afxolelockapp)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h  

##  <a name="a-nameafxoleregisterserverclassa--afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
 이 함수를 사용 하면 OLE 시스템 레지스트리에 있는 서버를 등록할 수 있습니다.  
  
```   
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszShortTypeName,  
    LPCTSTR lpszLongTypeName,  
    OLE_APPTYPE nAppType = OAT_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL); 
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 OLE 클래스 id입니다. 서버에 대 한 참조  
  
 `lpszClassName`  
 서버 개체의 클래스 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *lpszShortTypeName*  
 "차트입니다."와 같은 서버의 개체 형식의 짧은 이름을 포함 하는 문자열에 대 한 포인터  
  
 *lpszLongTypeName*  
 "Microsoft Excel 5.0 차트입니다."와 같은 서버의 개체 유형의 긴 이름을 포함 하는 문자열에 대 한 포인터  
  
 `nAppType`  
 가져온 값의 **OLE_APPTYPE** OLE 응용 프로그램의 유형을 지정 하는 열거형입니다. 가능한 값은 다음과 같습니다.  
  
- `OAT_INPLACE_SERVER`서버에는 전체 서버 사용자 인터페이스에 있습니다.  
  
- `OAT_SERVER`서버 지원만 포함 합니다.  
  
- `OAT_CONTAINER`컨테이너 지원 링크를 포함 합니다.  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-가능 개체입니다.  
  
 `rglpszRegister`  
 키와 키에 대 한 기존 값이 없는 발견 되 면 OLE 시스템 레지스트리에 추가 될 값을 나타내는 문자열에 대 한 포인터의 배열입니다.  
  
 `rglpszOverwrite`  
 키와 값을 레지스트리에 지정 된 키에 대 한 기존 값을 포함 하는 경우 OLE 시스템 레지스트리에 추가 하려면를 나타내는 문자열에 대 한 포인터의 배열입니다.  
  
### <a name="return-value"></a>반환 값  
 서버 클래스 성공적으로 등록 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 대부분의 응용 프로그램을 사용 하 여 수 **COleTemplateServer::Register** 를 응용 프로그램의 문서 유형을 등록 합니다. 응용 프로그램의 시스템 레지스트리 형식 대부분의 일반적인 패턴에 맞지 않을 경우 사용할 수 있습니다 `AfxOleRegisterServerClass` 제어 합니다.  
  
 레지스트리 키와 값의 집합으로 구성 됩니다. `rglpszRegister` 및 `rglpszOverwrite` 인수는 문자열에 대 한 포인터 배열, 구성 된 키와 값을 구분 하 여 한 **NULL** 문자 ( `'\0'`). 이 문자열의 각 해당 위치는 문자 시퀀스를 회색으로 표시 되는 대체 가능 매개 변수를 가질 수 있습니다 `%1` 통해 `%5`합니다.  
  
 기호에서 다음과 같이 작성 됩니다.  
  
|기호|값|  
|------------|-----------|  
|%1|문자열로 서식이 지정 된 클래스 ID|  
|%2|클래스 이름|  
|%3|실행 파일 경로를|  
|%4|짧은 형식 이름|  
|%5|긴 형식 이름|  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h

##  <a name="a-nameafxoleseteditmenua--afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 에 대 한 사용자 인터페이스를 구현 하는 *typename* 명령 개체입니다.  
  
```   
void  AFXAPI  AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pClient`  
 클라이언트 OLE 항목에 대 한 포인터입니다.  
  
 `pMenu`  
 업데이트할 메뉴 개체에 대 한 포인터입니다.  
  
 *iMenuItem*  
 업데이트할 메뉴 항목의 인덱스입니다.  
  
 `nIDVerbMin`  
 기본 동사에 해당 하는 명령 ID입니다.  
  
 *nIDVerbMax*  
 동사를 마지막으로 해당 하는 명령 ID입니다.  
  
 *nIDConvert*  
 Convert 메뉴 항목의 ID입니다.  
  
### <a name="remarks"></a>주의  
 서버는 기본 동사만 인식 하는 경우에 메뉴 항목 됩니다 "동사 *typename* 개체" 고 `nIDVerbMin` 명령이 사용자가 명령을 선택할 때 전송 됩니다. 서버는 몇 가지 동사를 인식 하는 경우 메뉴 항목은 " *typename* 개체" 동사를 모두 나열 하는 하위 메뉴 명령을 선택 하면 나타납니다. 하위 메뉴에서 동사를 선택할 때 `nIDVerbMin` 첫 번째 동사를 선택 하는 경우 전송 `nIDVerbMin` + 1의 두 번째 동사는 등 선택한 경우 전송 됩니다. 기본 `COleDocument` 구현에서이 기능을 자동으로 처리 합니다.  
  
 클라이언트의 응용 프로그램 리소스 스크립트에 다음 문이 있어야 (합니다. RC) 파일:  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxole.h 

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

