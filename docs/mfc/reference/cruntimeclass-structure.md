---
title: "CRuntimeClass 구조 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CRuntimeClass structure
- dynamic class information
- runtime, class information
- run-time class, CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 17994895aec5eee3fbe67bef5f80494988906df9
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cruntimeclass-structure"></a>CRuntimeClass 구조
각 클래스에서 파생 된 `CObject` 과 연관는 `CRuntimeClass` 런타임에 개체 또는 해당 기본 클래스에 대 한 정보를 가져오는 데 사용할 수 있는 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CRuntimeClass  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRuntimeClass::CreateObject](#createobject)|런타임 동안 개체를 만듭니다.|  
|[CRuntimeClass::FromName](#fromname)|친숙 한 클래스 이름을 사용 하 여 런타임에 개체를 만듭니다.|  
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|지정된 된 클래스에서 파생 된 클래스에는 경우를 결정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|클래스의 이름입니다.|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|개체의 크기(바이트)입니다.|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|에 대 한 포인터는 `CRuntimeClass` 기본 클래스의 구조입니다.|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|동적으로 개체를 생성 하는 함수에 대 한 포인터입니다.|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|반환 된 `CRuntimeClass` (때 동적으로 사용할 수 있는 연결)만 구성 합니다.|  
|[CRuntimeClass::m_wSchema](#m_wschema)|클래스의 스키마 수입니다.|  
  
## <a name="remarks"></a>주의  
 `CRuntimeClass`구조 이며 따라서 기본 클래스를 필요가 없습니다.  
  
 런타임 시 개체의 클래스를 확인 하는 기능 함수 인수를 검사 하는 추가 형식을 필요한 경우 또는 개체의 클래스를 기반으로 하는 특수 한 용도의 코드를 작성 해야 하는 경우에 유용 합니다. 런타임 클래스 정보는 c + + 언어에서 직접 지원 되지 않습니다.  
  
 `CRuntimeClass`에 대 한 포인터와 같은 관련된 c + + 개체에 대해 설명 된 `CRuntimeClass` 기본 클래스 및 관련된 클래스의 ASCII 클래스 이름입니다. 이 구조는 또한 동적으로 개체를 친숙 한 이름을 사용 하 고 관련된 클래스는 특정 클래스에서 파생 된 경우를 결정 하 여 개체의 형식 지정을 만드는 데 사용할 수 있는 다양 한 기능을 구현 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CRuntimeClass`, 문서를 참조 하십시오 [런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CRuntimeClass`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="createobject"></a>CRuntimeClass::CreateObject  
 동적으로 런타임에 지정된 된 클래스를 만들려면이 함수를 호출 합니다.  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 클래스를 만들 수의 친숙 한 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 개체에 대 한 포인터 또는 **NULL** 클래스 이름이 발견 되지 않으면 또는 메모리가 부족 한 개체를 만드는 경우.  
  
### <a name="remarks"></a>주의  
 클래스에서 파생 된 `CObject` 런타임에 지정된 된 클래스의 개체를 만들 수 있는 동적 생성을 지원할 수 있습니다. 문서, 뷰 및 프레임 클래스, 예를 들어 해야 동적 생성을 지원 합니다. 동적 만들기에 대 한 자세한 내용은 및 `CreateObject` 멤버 참조 [CObject 클래스](../../mfc/using-cobject.md) 및 [CObject 클래스: 기능 수준 지정](../../mfc/specifying-levels-of-functionality.md)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="fromname"></a>CRuntimeClass::FromName  
 검색 하려면이 함수 호출의 `CRuntimeClass` 친숙 한 이름에 연결 된 구조입니다.  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 파생 된 클래스의 친숙 한 이름을 `CObject`합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CRuntimeClass` 이름에 해당 하는 전달 된 개체 `lpszClassName`합니다. 함수 반환 **NULL** 일치 하는 클래스 이름이 없는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample #&17;](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>CRuntimeClass::IsDerivedFrom  
 이 함수를 호출 하는 클래스에 지정 된 클래스에서 파생 됩니다 확인 호출의 *pBaseClass* 매개 변수입니다.  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 *pBaseClass*  
 파생 된 클래스의 친숙 한 이름을 `CObject`합니다.  
  
### <a name="return-value"></a>반환 값  
 **TRUE** 경우 클래스를 호출 하는 `IsDerivedFrom` 기본에서 파생 된 클래스 `CRuntimeClass` 구조는 매개 변수로 지정 하 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 관계 "단계별로 수행 하 여" 파생 된 클래스의 체인을 해당 멤버의 클래스에서 위쪽으로 결정 됩니다. 이 함수는 반환만 **FALSE** 기본 클래스에 대 한 일치 항목이 없을 경우.  
  
> [!NOTE]
>  사용 하는 `CRuntimeClass` 포함 해야 구조는 `IMPLEMENT_DYNAMIC`, `IMPLEMENT_DYNCREATE`, 또는 `IMPLEMENT_SERIAL` 런타임 개체 정보를 검색 하려는 클래스의 구현에서 매크로입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CRuntimeClass`, 문서를 참조 하십시오 [CObject 클래스: 런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample #&18;](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName  
 ASCII 클래스 이름이 포함 된 null로 끝나는 문자열입니다.  
  
### <a name="remarks"></a>주의  
 이 이름을 사용 하 여 클래스의 인스턴스를 만드는 데 사용할 수는 `FromName` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize  
 크기 (바이트)는 개체입니다.  
  
### <a name="remarks"></a>주의  
 개체에 데이터 멤버가 할당 된 메모리를 가리키는 경우 해당 메모리의 크기가 포함 되지 않습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass  
 이 데이터 멤버에 대 한 포인터를 포함 하는 경우 응용 프로그램은 정적으로 MFC에 링크를 `CRuntimeClass` 기본 클래스의 구조입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램은 동적으로 MFC 라이브러리에 링크를 참조 [m_pfnGetBaseClass](#m_pfngetbaseclass)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject  
 클래스의 개체를 만드는 기본 생성자 함수 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 포인터 에서만 유효 클래스가 동적 생성; 지원 그렇지 않으면 함수가 반환 **NULL**합니다.  
  
##  <a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass  
 이 데이터 멤버를 반환 하는 함수를 가리키는 공유 DLL로 MFC 라이브러리를 사용 하는 응용 프로그램을 경우는 `CRuntimeClass` 기본 클래스의 구조입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램은 정적으로 MFC 라이브러리에 링크를 참조 [m_pBaseClass](#m_pbaseclass)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="m_wschema"></a>CRuntimeClass::m_wSchema  
 스키마 (직렬화 할 수 없는 클래스에 대 한-1) 수입니다.  
  
### <a name="remarks"></a>주의  
 스키마 숫자에 대 한 자세한 내용은 참조는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)   
 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)   
 [RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)   
 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)   
 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)   
 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)




