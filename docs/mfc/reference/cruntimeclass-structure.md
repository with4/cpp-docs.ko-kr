---
title: CRuntimeClass 구조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 365247dc41ea75e67f63b2bb76b5bfe0c14a7ead
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass 구조
각 클래스에서 파생 된 `CObject` 연관는 `CRuntimeClass` 런타임에 개체 또는 해당 기본 클래스에 대 한 정보를 가져오는 데 사용할 수 있는 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CRuntimeClass  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRuntimeClass::CreateObject](#createobject)|런타임 중 개체를 만듭니다.|  
|[CRuntimeClass::FromName](#fromname)|친숙 한 클래스 이름을 사용 하 여 런타임 중 개체를 만듭니다.|  
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|클래스는 지정된 된 클래스에서 파생 된 경우를 결정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|클래스의 이름입니다.|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|개체의 크기(바이트)입니다.|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|에 대 한 포인터는 `CRuntimeClass` 기본 클래스의 구조입니다.|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|개체를 동적으로 생성 하는 함수에 대 한 포인터입니다.|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|반환 된 `CRuntimeClass` (때 동적으로 사용할 수 있는 연결)만 구성 합니다.|  
|[CRuntimeClass::m_wSchema](#m_wschema)|클래스의 스키마 수입니다.|  
  
## <a name="remarks"></a>설명  
 `CRuntimeClass` 구조체가 고 기본 클래스도 있습니다.  
  
 런타임 시 개체의 클래스를 결정 하는 기능 추가 형식 함수 인수 검사가 필요할 때 또는 개체의 클래스에 기반 하는 특수 한 용도의 코드를 작성 해야 하는 경우에 유용 합니다. 런타임 클래스 정보는 c + + 언어에서 직접 지원 되지 않습니다.  
  
 `CRuntimeClass` 에 대 한 포인터와 같은 관련된 c + + 개체에 대 한 정보를 제공는 `CRuntimeClass` 기본 클래스 및 관련된 클래스의 ASCII 클래스 이름입니다. 이 구조는 또한 친숙 한 이름을 사용 하 고 관련된 클래스 특정 클래스에서 파생 된 경우를 결정 하 여 개체의 유형을 지정 하는 개체를 동적으로 만들 데 사용할 수 있는 다양 한 기능을 구현 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CRuntimeClass`, 문서를 참조 [런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CRuntimeClass`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="createobject"></a>  CRuntimeClass::CreateObject  
 런타임 중 지정된 된 클래스를 만들려면 동적으로이 함수를 호출 합니다.  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 클래스를 만들 수의 친숙 한 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 개체에 대 한 포인터 또는 **NULL** 클래스 이름의 찾을 발생 하거나 메모리가 부족 하 여 개체를 만듭니다.  
  
### <a name="remarks"></a>설명  
 클래스에서 파생 된 `CObject` 런타임 시 지정된 된 클래스의 개체를 만들 수 있는 동적 만들기를 지원할 수 있습니다. 문서, 뷰 및 프레임 클래스, 예를 들어 해야 동적 생성을 지원 합니다. 동적 만들기에 대 한 자세한 내용은 및 `CreateObject` 멤버 참조 [CObject 클래스](../../mfc/using-cobject.md) 및 [CObject 클래스: 기능 수준 지정](../../mfc/specifying-levels-of-functionality.md)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="fromname"></a>  CRuntimeClass::FromName  
 검색 하려면이 함수 호출의 `CRuntimeClass` 친숙 한 이름에 연결 된 구조입니다.  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 파생 된 클래스의 친숙 한 이름을 `CObject`합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CRuntimeClass` 이름에 해당 하는 전달 된 개체 `lpszClassName`합니다. 함수 반환 **NULL** 경우 일치 하는 클래스 이름을 찾지 못했습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>  CRuntimeClass::IsDerivedFrom  
 이 함수를 호출 하는 클래스에 지정 된 클래스에서 파생 됩니다 확인 호출의 *pBaseClass* 매개 변수입니다.  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 *pBaseClass*  
 파생 된 클래스의 친숙 한 이름을 `CObject`합니다.  
  
### <a name="return-value"></a>반환 값  
 **TRUE** 경우 클래스 호출 `IsDerivedFrom` 기본에서 파생 된 클래스 `CRuntimeClass` 구조를 매개 변수로 지정 되지 않았으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 관계 "를 검색 하 여" 파생 된 클래스의 체인을 해당 멤버의 클래스에서 위쪽으로 결정 됩니다. 이 함수는만 반환 **FALSE** 기본 클래스에 대 한 일치 항목이 없을 경우.  
  
> [!NOTE]
>  사용 하는 `CRuntimeClass` 포함 해야 구조는 `IMPLEMENT_DYNAMIC`, `IMPLEMENT_DYNCREATE`, 또는 `IMPLEMENT_SERIAL` 런타임에 개체 정보를 검색 하려는 클래스의 구현에서 매크로입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CRuntimeClass`, 문서를 참조 [CObject 클래스: 런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>  CRuntimeClass::m_lpszClassName  
 ASCII 클래스 이름이 포함 된 null로 끝나는 문자열입니다.  
  
### <a name="remarks"></a>설명  
 이 이름을 사용 하 여 클래스의 인스턴스를 만드는 데 사용할 수는 `FromName` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="m_nobjectsize"></a>  CRuntimeClass::m_nObjectSize  
 크기 (바이트)에서 개체입니다.  
  
### <a name="remarks"></a>설명  
 개체에 데이터 멤버가 할당 된 메모리에 해당 지점 해당 메모리의 크기가 포함 되지 않습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="m_pbaseclass"></a>  CRuntimeClass::m_pBaseClass  
 이 데이터 멤버에 대 한 포인터를 포함 하는 경우 응용 프로그램은 정적으로 MFC에 링크를 `CRuntimeClass` 기본 클래스의 구조입니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램 동적으로 MFC 라이브러리에 연결 하는 경우 참조 [m_pfnGetBaseClass](#m_pfngetbaseclass)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="m_pfncreateobject"></a>  CRuntimeClass::m_pfnCreateObject  
 클래스의 개체를 만드는 기본 생성자 함수 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 포인터 에서만 유효 클래스가; 동적 만들기를 지원 합니다. 그렇지 않으면 함수가 반환 **NULL**합니다.  
  
##  <a name="m_pfngetbaseclass"></a>  CRuntimeClass::m_pfnGetBaseClass  
 이 데이터 멤버를 반환 하는 함수를 가리키는 MFC 라이브러리를 공유 DLL로 사용 하는 응용 프로그램을 하는 경우는 `CRuntimeClass` 기본 클래스의 구조입니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램은 정적으로 MFC 라이브러리에 링크를 참조 [m_pBaseClass](#m_pbaseclass)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [IsDerivedFrom](#isderivedfrom)합니다.  
  
##  <a name="m_wschema"></a>  CRuntimeClass::m_wSchema  
 스키마 (직렬화 할 수 없는 클래스에 대 한-1) 수입니다.  
  
### <a name="remarks"></a>설명  
 스키마 번호에 대 한 자세한 내용은 참조는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로입니다.  
  
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



