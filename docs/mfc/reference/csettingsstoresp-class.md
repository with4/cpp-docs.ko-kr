---
title: "CSettingsStoreSP 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cf9659b6c367146a565834bd65fdfc9f28a9812
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP 클래스
`CSettingsStoreSP` 클래스는 인스턴스를 만드는 데 사용할 수 있는 도우미 클래스는 [CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|`CSettingsStoreSP` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|파생 된 클래스의 인스턴스를 만들고 `CSettingsStore`합니다.|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|런타임 클래스를 설정합니다. `Create` 메서드는 런타임 클래스를 사용 하 여 만들려는 개체의 클래스를 결정 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|`m_dwUserData`|에 저장 된 사용자 지정 사용자 데이터는 `CSettingsStoreSP` 개체입니다. 생성자에서이 데이터를 제공는 `CSettingsStoreSP` 개체입니다.|  
|`m_pRegistry`|`CSettingsStore`-파생 된 개체는 `Create` 메서드를 만듭니다.|  
  
## <a name="remarks"></a>설명  
 사용할 수는 `CSettingsStoreSP` 클래스는 XML 파일 또는 데이터베이스 등의 다른 위치에 모든 MFC 레지스트리 작업을 리디렉션할 수 있습니다. 이렇게 하려면 다음 단계를 수행합니다.  
  
1.  클래스를 만듭니다 (예: `CMyStore`)에서 파생 하 고 `CSettingsStore`합니다.  
  
2.  사용 하 여 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) 및 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) 사용자 지정 된 매크로가 `CSettingsStore` 클래스를 사용 하는 동적 생성 합니다.  
  
3.  가상 함수를 재정의 하 고 구현 된 `Read` 및 `Write` 사용자 지정 클래스의 함수입니다. 데이터 읽기 및 쓰기를 통해 원하는 위치에 다른 기능을 구현 합니다.  
  
4.  응용 프로그램에서 호출 `CSettingsStoreSP::SetRuntimeClass` 전달에 대 한 포인터는 [CRuntimeClass 구조](../../mfc/reference/cruntimeclass-structure.md) 클래스에서 가져옵니다.  
  
 프레임 워크는 주로 레지스트리를 액세스 하 고, 때마다 이제 동적으로 사용자 지정 클래스를 인스턴스화할 되며 데이터를 사용 합니다.  
  
 `CSettingsStoreSP::SetRuntimeClass`전역 정적 변수를 사용 합니다. 따라서 하나의 사용자 지정 저장소를 한 번에 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxsettingsstore.h  
  
##  <a name="create"></a>CSettingsStoreSP::Create  
 파생 된 개체의 새 인스턴스를 만듭니다는 [CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)합니다.  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bAdmin`  
 결정 하는 부울 매개 변수 여부는 `CSettingsStore` 관리자 모드에서 개체가 만들어집니다.  
  
 [in] `bReadOnly`  
 결정 하는 부울 매개 변수 여부는 `CSettingsStore` 개체가 읽기 전용 액세스를 위해 만들어집니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든에 대 한 참조 `CSettingsStore` 개체입니다.  
  
### <a name="remarks"></a>설명  
 메서드를 사용 하면 [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) 개체의 유형을 확인 하려면 `CSettingsStoreSP::Create` 만들어집니다. 기본적으로이 메서드는 만듭니다는 `CSettingsStore` 개체입니다.  
  
 만드는 경우는 `CSettingsStore` 레지스트리에 대 한 모든 액세스에 대 한 기본 위치는 HKEY_LOCAL_MACHINE 관리자 모드에서 개체입니다. 그렇지 않으면 모든 레지스트리 액세스에 대 한 기본 위치는 HKEY_CURRENT_USER 합니다.  
  
 경우 `bAdmin` 은 `TRUE`, 응용 프로그램에 관리 권한이 있어야 합니다. 그렇지 않으면 레지스트리에 액세스 하려고 하면 실패 합니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 사용 하는 `Create` 의 메서드는 `CSettingsStoreSP` 클래스.  
  
 [!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="csettingsstoresp"></a>CSettingsStoreSP::CSettingsStoreSP  
 생성 된 [CSettingsStoreSP 클래스](../../mfc/reference/csettingsstoresp-class.md) 개체입니다.  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwUserData`  
 사용자 정의 데이터를는 `CSettingsStoreSP` 저장소 개체입니다.  
  
### <a name="remarks"></a>설명  
 `CSettingsStoreSP` 개체에서 데이터를 저장 `dwUserData` 보호 된 멤버 변수에 `m_dwUserData`합니다.  
  
##  <a name="setruntimeclass"></a>CSettingsStoreSP::SetRuntimeClass  
 런타임 클래스를 설정합니다. 메서드가 [CSettingsStoreSP::Create](#create) 런타임 클래스를 사용 하 여 만들 개체의 종류를 결정 합니다.  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRTI`  
 파생 된 클래스에 대 한 런타임 클래스 정보에 대 한 포인터는 [CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`성공 하면 `FALSE` 으로 클래스를 식별 하는 경우 `pRTI` 에서 파생 되지 않은 `CSettingsStore`합니다.  
  
### <a name="remarks"></a>설명  
 사용할 수는 [CSettingsStoreSP 클래스](../../mfc/reference/csettingsstoresp-class.md) 에서 클래스를 파생 `CSettingsStore`합니다. 메서드를 사용 하 여 `SetRuntimeClass` 에서 파생 된 사용자 지정 클래스의 개체를 만들려는 경우 `CSettingsStore`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)
