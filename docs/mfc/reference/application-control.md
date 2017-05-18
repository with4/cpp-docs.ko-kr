---
title: "응용 프로그램 제어 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 5e48437920f56cdfd119c1d703db585616881833
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="application-control"></a>응용 프로그램 컨트롤
OLE 응용 프로그램 및 해당 개체에 대 한 상당한 제어가 필요합니다. OLE 시스템 Dll을 시작한 다음 및 응용 프로그램을 자동으로 릴리스, 해당 프로덕션 및 개체의 수정 조정 등 수 있어야 합니다. 이 항목의 함수에는 이러한 요구 사항을 충족 합니다. OLE 시스템 Dll에서 호출 되는 것 외에도 이러한 함수도 응용 프로그램에서 라고도 합니다. 
  
### <a name="application-control"></a>응용 프로그램 컨트롤  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|응용 프로그램이 종료될 수 있는지 여부를 나타냅니다.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|응용 프로그램의 현재 메시지 필터를 검색합니다.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|현재 사용자 제어 플래그를 검색합니다.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|설정 하거나 사용자 정의 컨트롤 플래그를 지웁니다.|  
|[AfxOleLockApp](#afxolelockapp)|응용 프로그램의 활성 개체 수의 프레임 워크의 글로벌 수를 늘립니다.|  
|[AfxOleLockControl](#afxolelockcontrol)| 지정된 된 컨트롤의 클래스 팩터리를 잠급니다. |
|[AfxOleUnlockApp](#afxoleunlockapp)|감소 응용 프로그램의 활성 개체 수의 프레임 워크의 수입니다.| 
|[AfxOleUnlockControl](#afxoleunlockcontrol)| 지정된 된 컨트롤의 클래스 팩터리를 잠금 해제합니다. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE 시스템 레지스트리에 서버를 등록합니다.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|에 대 한 사용자 인터페이스를 구현 하는 *typename* 명령 개체입니다.|  

  
##  <a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 응용 프로그램이 종료될 수 있는지 여부를 나타냅니다.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>반환 값  
 응용 프로그램이 종료될 수 있으면 0이 아닌 값이고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 개체에 대해 해결되지 않은 참조가 있으면 응용 프로그램이 종료될 수 없습니다. 전역 함수 `AfxOleLockApp` 및 `AfxOleUnlockApp`은 각각 응용 프로그램의 개체에 대한 참조 수를 늘리거나 줄입니다. 이 카운터가 0이 아니면 응용 프로그램이 종료될 수 없습니다. 카운터가 0이 아니면 사용자가 시스템 메뉴에서 닫기를 선택하거나 파일 메뉴에서 종료를 선택할 때 응용 프로그램의 기본 창이 숨겨집니다(제거되지 않음). 프레임 워크이 함수를 호출 **cframewnd:: Onclose**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAutomation # 2](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h 

##  <a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 응용 프로그램의 현재 메시지 필터를 검색합니다.  
  
```   
COleMessageFilter* AFXAPI AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>반환 값  
 현재 메시지 필터에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 에 현재 액세스 하려면이 함수를 호출 `COleMessageFilter`-파생 된 개체를 호출 하는 것 처럼 `AfxGetApp` 현재 응용 프로그램 개체에 액세스할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAutomation # 3](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation # 4](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxwin.h 

##  <a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 현재 사용자 제어 플래그를 검색합니다.  
  
```   
BOOL AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>반환 값  
 사용자가 응용 프로그램을 제어 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용자가 응용 프로그램의 컨트롤에 사용자가 명시적으로 열거나 새 문서를 만들 때. 해당 사용자가 컨트롤에는 응용 프로그램이 OLE 시스템 Dll에 의해 시작 되지 경우-즉, 사용자 시스템 셸 사용 하 여 응용 프로그램을 시작 하는 경우.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 설정 하거나 해제에 대 한 참조에 설명 된 사용자 정의 컨트롤 플래그 `AfxOleGetUserCtrl`합니다.  
  
```  
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>매개 변수  
 *bUserCtrl*  
 사용자 제어 플래그 설정 하거나 지울 수를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크가이 함수를 호출 하지만 사용자가 만들거나, 문서를 로드 하는 경우 문서가 로드 되거나 포함된 된 개체 컨테이너 응용 프로그램에서 로드 하는 등의 간접 작업을 통해 만들지 때가 아니라 합니다.  
  
 응용 프로그램에서 다른 작업은 응용 프로그램의 컨트롤에 사용자를 입력 해야 하는 경우이 함수를 호출 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h

##  <a name="afxolelockapp"></a>AfxOleLockApp  
 응용 프로그램의 활성 개체 수의 프레임 워크의 글로벌 수를 늘립니다.  
  
```   
void AFXAPI AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>주의  
 프레임 워크 응용 프로그램에서 활성 개체 수의 개수를 유지합니다. `AfxOleLockApp` 및 `AfxOleUnlockApp` 함수 각각 증가 및이 횟수를 감소 시키기 합니다.  
  
 사용자가 활성 개체를 가진 응용 프로그램을 닫을 하려고 할 때-활성 개체 수는 0이 아닌 응용 프로그램-프레임 워크는 완전히 종료 되지 않고 사용자의 보기에서 응용 프로그램을 숨깁니다. `AfxOleCanExitApp` 함수 응용 프로그램이 종료 될 수 있는지 여부를 나타냅니다.  
  
 호출 `AfxOleLockApp` 에서 클라이언트 응용 프로그램에서 사용 되는 동안 제거 되도록 해당 개체에 적합 하지 않을 수는 경우 OLE 인터페이스를 노출 하는 개체입니다. 호출 또한 `AfxOleUnlockApp` 를 호출 하는 모든 개체의 소멸자에서 `AfxOleLockApp` 생성자에서 합니다. 기본적으로 `COleDocument` (및 파생 클래스) 자동으로 잠금 및 응용 프로그램 잠금을 해제 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAutomation # 5](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h

##  <a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 감소 프레임 워크의 응용 프로그램의 활성 개체 수입니다.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>설명  
 참조 `AfxOleLockApp` 자세한 정보.  
  
 활성 개체 수가 0에 도달 하면 **AfxOleOnReleaseAllObjects** 호출 됩니다.  
  
### <a name="example"></a>예제  
 예를 참조 [AfxOleLockApp](#afxolelockapp)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h  

 ## <a name="afxolelockcontrol"></a>AfxOleLockControl
컨트롤과 연결된 동적으로 생성된 데이터가 메모리에 유지되도록 지정된 컨트롤의 클래스 팩터리를 잠급니다.  
   
### <a name="syntax"></a>구문    
```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );  
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>매개 변수  
 `clsid`  
 컨트롤의 고유 클래스 ID입니다.  
  
 `lpszProgID`  
 컨트롤의 고유 프로그램 ID입니다.  
   
### <a name="return-value"></a>반환 값  
 컨트롤의 클래스 팩터리가 성공적으로 잠겼을 경우 0이 아닌 값이고, 그렇지 않으면 0입니다.  
   
### <a name="remarks"></a>주의  
 이렇게 하면 컨트롤 표시 속도가 상당히 빨라질 수 있습니다. 예를 들어 대화 상자에서 컨트롤을 만들고 이 컨트롤을 `AfxOleLockControl`로 잠글 경우에는 대화 상자를 표시 또는 삭제할 때마다 대화 상자를 만들고 종료할 필요가 없습니다. 사용자가 대화 상자를 반복해서 열고 닫는 경우, 컨트롤을 잠그면 성능이 크게 향상될 수 있습니다. 컨트롤을 삭제할 준비가 되면 `AfxOleUnlockControl`을 호출합니다.  
   
### <a name="example"></a>예제  
```cpp
// Starts and locks control's (Microsoft Calendar) class factory. 
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```
   
### <a name="requirements"></a>요구 사항  
 **헤더:**<afxwin.h></afxwin.h>  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [AfxOleUnlockControl](#afxoleunlockcontrol)
 
##  <a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
 이 함수를 사용 하면 OLE 시스템 레지스트리에 서버를 등록할 수 있습니다.  
  
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
 OLE 클래스 ID는 서버에 대 한 참조  
  
 `lpszClassName`  
 서버 개체의 클래스 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *lpszShortTypeName*  
 "차트"와 같은 서버의 개체 형식의 짧은 이름을 포함 하는 문자열에 대 한 포인터  
  
 *lpszLongTypeName*  
 "Microsoft Excel 5.0 차트입니다."와 같은 서버의 개체 형식의 긴 이름을 포함 하는 문자열에 대 한 포인터  
  
 `nAppType`  
 가져온 값의 **OLE_APPTYPE** OLE 응용 프로그램의 유형을 지정 하는 열거형입니다. 가능한 값은 다음과 같습니다.  
  
- `OAT_INPLACE_SERVER`서버에는 전체 서버 사용자 인터페이스에 있습니다.  
  
- `OAT_SERVER`서버 지원만 포함 합니다.  
  
- `OAT_CONTAINER`컨테이너는 포함 문서가에 대 한 링크를 지원합니다.  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-수 있는 개체입니다.  
  
 `rglpszRegister`  
 키와 키에 대 한 기존 값이 없는 발견 되 면 OLE 시스템 레지스트리에 추가 될 값을 나타내는 문자열에 대 한 포인터의 배열입니다.  
  
 `rglpszOverwrite`  
 키와 값을 레지스트리에 지정 된 키에 대 한 기존 값을 포함 하는 경우 OLE 시스템 레지스트리에 추가 하려면를 나타내는 문자열에 대 한 포인터의 배열입니다.  
  
### <a name="return-value"></a>반환 값  
 서버 클래스 성공적으로 등록 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 대부분의 응용 프로그램 צ ְ ײ **COleTemplateServer::Register** 를 응용 프로그램의 문서 유형을 등록 합니다. 응용 프로그램의 시스템 레지스트리 형식 대부분의 일반적인 패턴에 맞지 않을 경우 사용할 수 있습니다 `AfxOleRegisterServerClass` 더 많은 제어에 대 한 합니다.  
  
 레지스트리 키와 값의 집합으로 구성 됩니다. `rglpszRegister` 및 `rglpszOverwrite` 인수는 문자열에 대 한 포인터 배열, 구성 된 키와 값을 구분 하 여 한 **NULL** 문자 ( `'\0'`). 해당 위치는 문자 시퀀스 회색으로 표시 되는 대체 가능 매개 변수를 가질 수 있습니다 이러한 문자열 `%1` 통해 `%5`합니다.  
  
 기호는 다음과 같이 채워집니다.  
  
|기호|값|  
|------------|-----------|  
|%1|문자열로 서식이 지정 된 클래스 ID|  
|%2|클래스 이름|  
|%3|실행 파일 경로를|  
|%4|짧은 형식 이름|  
|%5|긴 형식 이름|  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 에 대 한 사용자 인터페이스를 구현 하는 *typename* 명령 개체입니다.  
  
```   
void AFXAPI AfxOleSetEditMenu(
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
 마지막에 해당 하는 동사 명령 ID입니다.  
  
 *nIDConvert*  
 Convert 메뉴 항목에 대 한 ID입니다.  
  
### <a name="remarks"></a>주의  
 서버는 기본 동사만 인식 하는 경우에 메뉴 항목 됩니다 "동사 *typename* 개체" 및 `nIDVerbMin` 명령이 사용자가 명령을 선택할 때 전송 됩니다. 서버가 여러 동사 인식 경우 메뉴 항목은 " *typename* 개체" 모든 동사를 나열 하는 하위 메뉴 명령을 선택 하면 나타납니다. 하위 메뉴에서 동사를 선택 하면 `nIDVerbMin` 첫 번째 동사를 선택한 경우 전송 `nIDVerbMin` + 1는 두 번째 동사가 등 선택한 경우 전송 됩니다. 기본 `COleDocument` 구현이이 기능을 자동으로 처리 합니다.  
  
 클라이언트의 응용 프로그램 리소스 스크립트에 다음 문이 있어야 (합니다. RC) 파일:  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>요구 사항  
 **헤더**: afxole.h 

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a>AfxOleUnlockControl
지정된 된 컨트롤의 클래스 팩터리를 잠금 해제합니다.  
   
### <a name="syntax"></a>구문  
  ```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );  
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>매개 변수  
 `clsid`  
 컨트롤의 고유 클래스 ID입니다.  
  
 `lpszProgID`  
 컨트롤의 고유 프로그램 ID입니다.  
   
### <a name="return-value"></a>반환 값  
 컨트롤의 클래스 팩터리가 성공적으로 잠금; 하지 않았으면 0이 아닌 그렇지 않으면 0입니다.  
   
### <a name="remarks"></a>주의  
 컨트롤은로 잠긴 `AfxOleLockControl`컨트롤과 연결 된 동적으로 생성된 된 데이터는 메모리에 남아 있도록 합니다. 이 수 표시 속도가 상당히 빨라질 컨트롤의 컨트롤을 만들고 제거 될 때마다 표시 되는 수 필요 하기 때문에 있습니다. 컨트롤을 삭제할 준비가 되면 `AfxOleUnlockControl`을 호출합니다.  
   
### <a name="example"></a>예제  
 ```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));

```
   
### <a name="requirements"></a>요구 사항  
 **헤더:**<afxwin.h></afxwin.h>  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)  
 [AfxOleLockControl](#afxolelockcontrol)


