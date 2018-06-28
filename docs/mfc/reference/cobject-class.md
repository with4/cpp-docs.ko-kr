---
title: CObject 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
dev_langs:
- C++
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34babea47abaab9fcfb45f57aedd5cec94e82963
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041713"
---
# <a name="cobject-class"></a>CObject 클래스
MFC 라이브러리의 주체 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CObject::CObject](#cobject)|기본 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CObject::AssertValid](#assertvalid)|이 개체의이 무결성을 확인 합니다.|  
|[CObject::Dump](#dump)|이 개체의 진단 덤프를 생성 합니다.|  
|[CObject::GetRuntimeClass](#getruntimeclass)|반환 된 `CRuntimeClass` 이 개체의 클래스에 해당 하는 구조입니다.|  
|[CObject::IsKindOf](#iskindof)|지정된 된 클래스의이 개체의이 관계를 테스트합니다.|  
|[CObject::IsSerializable](#isserializable)|이 개체를 serialize 할 수 있는지 여부를 확인 하려면 테스트 합니다.|  
|[Cobject:: Serialize](#serialize)|로드 하거나 보낸 사람/받는 보관 파일 개체를 저장 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CObject::operator 삭제](#operator_delete)|특별 한 **삭제** 연산자입니다.|  
|[새 CObject::operator](#operator_new)|특별 한 **새** 연산자입니다.|  
  
## <a name="remarks"></a>설명  
 와 같은 라이브러리 클래스에 대 한 뿐만 아니라 루트로 사용 `CFile` 및 `CObList`, 하지만 사용자가 작성 된 클래스에 대 한도입니다. `CObject` 기본 서비스를 포함 하 여 제공  
  
-   Serialization 지원  
  
-   런타임 클래스 정보  
  
-   개체 진단 출력  
  
-   컬렉션 클래스와의 호환성  
  
 `CObject` 다중 상속을 지원 하지 않습니다. 파생된 클래스에 하나씩만 있을 수 `CObject` 기본 클래스와 `CObject` 계층 구조에서 가장 왼쪽에 있어야 합니다. 그러나 것은 허용 가능한 구조가 있을 수 및 비- `CObject`-오른쪽 다중 상속 분기에서 파생 된 클래스가 있습니다.  
  
 주요 혜택을 얻게 될 `CObject` 파생 클래스 구현 및 선언에서 선택적 매크로 중 일부를 사용 하는 경우.  
  
 첫 번째 수준의 매크로 [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) 및 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), 클래스 이름 및 계층 구조에서 해당 위치에 대 한 런타임 액세스를 허용 합니다. 이 하면 진단 덤핑을 의미 합니다.  
  
 2-수준 매크로 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)에서 첫 번째 수준의 매크로의 모든 기능을 포함 하 고 사용 하는 serialize 할 개체에 ""와 "보관"입니다.  
  
 일반적으로 Microsoft Foundation 클래스와 c + + 클래스 파생 및 사용에 대 한 내용은 `CObject`, 참조 [CObject 사용 하 여](../../mfc/using-cobject.md) 및 [Serialization](../../mfc/serialization-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="assertvalid"></a>  CObject::AssertValid  
 이 개체의이 무결성을 확인 합니다.  
  
```  
virtual void AssertValid() const;  
```  
  
### <a name="remarks"></a>설명  
 `AssertValid` 내부 상태를 확인 하 여이 개체의 유효성 검사를 수행 합니다. 라이브러리의 디버그 버전에서 `AssertValid` assert 하 고 따라서 어설션이 실패 한 줄 번호와 파일 이름을 나열 하는 메시지를 사용 하 여 프로그램을 종료할 수 있습니다.  
  
 재정의 해야 클래스를 직접 작성 하는 경우는 `AssertValid` 자신 및 다른 사용자가 클래스에 대 한 진단 서비스를 제공 하는 함수입니다. 재정의 된 `AssertValid` 일반적으로 `AssertValid` 파생된 클래스에 고유한 데이터 멤버를 검사 하기 전에 기본 클래스의 함수입니다.  
  
 때문에 `AssertValid` 는 **const** 함수를 되지 허용 되는 경우 테스트 중 개체 상태를 변경 해야 합니다. 파생된 클래스를 직접 `AssertValid` 함수 예외를 throw 하지 않아야 하지만 대신 어설션하 잘못 된 개체 데이터를 검색 하 고 있는지 여부를 합니다.  
  
 "Validity"의 정의 개체의 클래스에 따라 달라 집니다. 일반적으로 함수 확인을 수행 해야 "단순 합니다." 즉, 한 개체가 다른 개체에 대 한 포인터를 포함 하는 경우에서 포인터가 null이 아닌 하지만 유효 포인터에서 참조 하는 개체에 대 한 테스트를 수행 하지 않아야 하는지 여부를 확인 하려면 확인 합니다.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 페이지에서 사용 되는 클래스 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 또 다른 예에 대 한 참조 [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects)합니다.  
  
##  <a name="cobject"></a>  CObject::CObject  
 이러한 함수는 표준 `CObject` 생성자입니다.  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 *objectSrc*  
 다른에 대 한 참조 `CObject`  
  
### <a name="remarks"></a>설명  
 기본 버전은 자동으로 파생 된 클래스의 생성자에 의해 호출 됩니다.  
  
 사용자 클래스를 직렬화 하는 경우 (IMPLEMENT_SERIAL 매크로 통합), 클래스 선언에서 기본 생성자 (인수 없는 생성자)를 갖고 있어야 합니다. 기본 생성자, 필요 하지 않은 경우에 private 선언 또는 "empty" 생성자를 보호 합니다. 자세한 내용은 참조 [CObject 사용 하 여](../../mfc/using-cobject.md)합니다.  
  
 표준 c + + 기본 클래스 복사 생성자는 멤버 별로 복사를 수행합니다. 개인의 존재 여부 `CObject` 복사 생성자는 클래스의 복사 생성자가 필요 하지만 사용할 수 없는 경우 컴파일러 오류 메시지를 보장 합니다. 따라서 클래스에이 기능을 요구 하는 경우 복사 생성자를 제공 해야 합니다.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 에 사용 되는 클래스는 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>  CObject::Dump  
 사용자 개체의 내용을 덤프는 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 개체입니다.  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *dc*  
 일반적으로 덤프 하는 동안 진단 덤프 컨텍스트 `afxDump`합니다.  
  
### <a name="remarks"></a>설명  
 재정의 해야 클래스를 직접 작성 하는 경우는 `Dump` 자신 및 다른 사용자가 클래스에 대 한 진단 서비스를 제공 하는 함수입니다. 재정의 된 `Dump` 일반적으로 `Dump` 파생된 클래스에 고유한 데이터 멤버를 인쇄 하기 전에 기본 클래스의 함수입니다. `CObject::Dump` 클래스를 사용 하는 경우 클래스 이름을 인쇄는 `IMPLEMENT_DYNAMIC` 또는 IMPLEMENT_SERIAL 매크로입니다.  
  
> [!NOTE]
>  프로그램 `Dump` 함수 출력의 끝에 줄 바꿈 문자를 인쇄 하지 해야 합니다.  
  
 `Dump` Microsoft Foundation Class 라이브러리의 디버그 버전에만 의미가 호출 합니다. 호출과 함수 선언 된 함수 구현에서는 대괄호 해야 **#ifdef _DEBUG** /  `#endif` 조건부 컴파일에 대 한 문입니다.  
  
 이후 `Dump` 는 **const** 함수 되지 허용 되는 경우 덤프 하는 동안 개체 상태를 변경 하려면.  
  
 [CDumpContext 삽입 (<<) 연산자](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) 호출 `Dump` 때는 `CObject` 포인터를 삽입 합니다.  
  
 `Dump` 개체의 "비순환"만 덤프를 허용 합니다. 예를 들어 개체 목록을 덤프 수 있지만 목록 자체 개체 중 하나 이면 결국 스택을 오버플로 합니다.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 페이지에서 사용 되는 클래스 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>  CObject::GetRuntimeClass  
 반환 된 `CRuntimeClass` 이 개체의 클래스에 해당 하는 구조입니다.  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조;이 개체의이 클래스에 해당 되지 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 하나의 `CRuntimeClass` 각각에 대 한 구조 `CObject`-클래스를 파생 합니다. 구조체 멤버는 다음과 같습니다.  
  
- **LPCSTR m_lpszClassName** ASCII 클래스 이름을 포함 하는 null로 끝나는 문자열.  
  
- **int m_nObjectSize** 바이트 단위로 개체의 크기입니다. 개체에 데이터 멤버가 할당 된 메모리에 해당 지점 해당 메모리의 크기가 포함 되지 않습니다.  
  
- **UINT m_wSchema** 스키마 번호 (-1 직렬화 할 수 없는 클래스에 대 한). 참조는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로 대 한 설명은 스키마 번호입니다.  
  
- **CObject\* (파스칼식\* m_pfnCreateObject) ()** 클래스의 개체를 만드는 기본 생성자에 대 한 함수 포인터 (유효한 클래스는 동적 생성을 지원 하는 경우에 이렇게 하지 않으면 반환 **NULL** ).  
  
- **CRuntimeClass\* (파스칼식\* m_pfn_GetBaseClass) ()** 응용 프로그램 AFXDLL 버전의 MFC에 동적으로 연결 되어, 함수에 대 한 포인터를 반환 하는 `CRuntimeClass` 기본 클래스의 구조입니다.  
  
- **CRuntimeClass\* m_pBaseClass** 응용 프로그램에 대 한 포인터, MFC에 정적으로 연결 됩니다는 `CRuntimeClass` 기본 클래스의 구조입니다.  
  
 이 함수를 사용 해야는 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), 또는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 클래스 구현에는 매크로입니다. 그렇지 않으면 잘못 된 결과 얻을 수 있습니다.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 페이지에서 사용 되는 클래스 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>  CObject::IsKindOf  
 지정된 된 클래스의이 개체의이 관계를 테스트합니다.  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pClass*  
 에 대 한 포인터는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조와 연결 된 프로그램 `CObject`-클래스를 파생 합니다.  
  
### <a name="return-value"></a>반환 값  
 개체 클래스에 해당 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 테스트 *pClass* 지정된 된 클래스의 개체는 (1) 또는 (2)은 지정된 된 클래스에서 파생 된 클래스의 개체입니다. 으로 선언 된 클래스에 대해서만 작동 하는이 함수는 [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), 또는 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 매크로입니다.  
  
 사용 하지 마십시오이 함수 광범위 하 게 하므로 c + + 다형성 기능 무효로 만듭니다. 가상 함수를 대신 사용 합니다.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 페이지에서 사용 되는 클래스 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>  CObject::IsSerializable  
 이 개체는 serialization에 사용할 수 있는지 테스트 합니다.  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 경우 0이 아닌 개체를 serialize 할 수 있습니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 직렬화 할 수는 클래스에 대 한 해당 선언 포함 되어야 합니다는 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 매크로 구현이 포함 해야 합니다는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로입니다.  
  
> [!NOTE]
>  이 함수를 재정의 하지 마십시오.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 페이지에서 사용 되는 클래스 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]  
  
##  <a name="operator_delete"></a>  CObject::operator 삭제  
 라이브러리의 릴리스 버전에 대 한 연산자 **삭제** 연산자가 할당 된 메모리를 해제 **새**합니다.  
  
```  
void PASCAL operator delete(void* p);

 
void PASCAL operator delete(
    void* p,
    void* pPlace);

 
void PASCAL operator delete(
    void* p,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>설명  
 디버그 버전에서 연산자 **삭제** 메모리 누수를 찾는 설계 할당 모니터링 체계에 참여 합니다.  
  
 코드 줄을 사용 하는 경우  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 이전에 구현에 한 합니다. CPP 파일을 다음의 세 번째 버전 **삭제** 사용 되며 나중에 보고를 위해 할당된 된 블록에 파일 이름과 줄 번호를 저장 합니다. 추가; 매개 변수를 제공 하는 방법에 대 한 걱정할 필요가 없습니다. 매크로를 처리합니다.  
  
 사용 하지 않는 경우에 `DEBUG_NEW` 디버그 모드에서 여전히 얻게 누수 탐지 없지만 위에서 설명한 소스 파일 줄 번호 보고 합니다.  
  
 연산자를 재정의 하는 경우 **새** 및 **삭제**, 진단이 기능을 상실 합니다.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 에 사용 되는 클래스는 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]  
  
##  <a name="operator_new"></a>  새 CObject::operator  
 라이브러리의 릴리스 버전에 대 한 연산자 **새** 최적의 메모리 할당을 유사한 방식으로 수행 `malloc`합니다.  
  
```  
void* PASCAL operator new(size_t nSize);  
void* PASCAL operator new(size_t, void* p);

 
void* PASCAL operator new(
    size_t nSize,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>설명  
 디버그 버전에서 연산자 **새** 메모리 누수를 찾는 설계 할당 모니터링 체계에 참여 합니다.  
  
 코드 줄을 사용 하는 경우  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 이전에 구현에 한 합니다. CPP 파일을 다음의 두 번째 버전 **새** 사용 되며 나중에 보고를 위해 할당된 된 블록에 파일 이름과 줄 번호를 저장 합니다. 추가; 매개 변수를 제공 하는 방법에 대 한 걱정할 필요가 없습니다. 매크로를 처리합니다.  
  
 사용 하지 않는 경우에 `DEBUG_NEW` 디버그 모드에서 여전히 얻게 누수 탐지 없지만 위에서 설명한 소스 파일 줄 번호 보고 합니다.  
  
> [!NOTE]
>  이 연산자를 재정의 하는 경우 재정의 해야 **삭제**합니다. 표준 라이브러리를 사용 하지 마십시오 **_new_handler** 함수입니다.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 에 사용 되는 클래스는 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>  Cobject:: Serialize  
 이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 *ar*  
 A `CArchive` 를 serialize 할 개체입니다.  
  
### <a name="remarks"></a>설명  
 재정의 해야 `Serialize` serialize 하려는 각 클래스에 대 한 합니다. 재정의 된 `Serialize` 먼저 호출 해야 합니다는 `Serialize` 기본 클래스의 함수입니다.  
  
 사용 해야는 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 클래스 선언에서 매크로 사용 해야 합니다는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로 구현에서 합니다.  
  
 사용 하 여 [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) 또는 [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) 을 보관 저장 로드 여부를 확인 합니다.  
  
 `Serialize` 호출한 [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) 및 [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject)합니다. 이러한 함수는 연관 된 `CArchive` 삽입 연산자 ( **< \<**) 및 추출 연산자 ( **>>**).  
  
 Serialization 예제를 보려면 문서 [Serialization: 개체를 직렬화](../../mfc/serialization-serializing-an-object.md)합니다.  
  
### <a name="example"></a>예  
 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) 목록은 `CAge` 모든 페이지에서 사용 되는 클래스 `CObject` 예제입니다.  
  
 [!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



