---
title: 'TN002: 영구 개체 데이터 형식 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca145ff871e1c5ccff27bdebe473c6cb6f39073a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tn002-persistent-object-data-format"></a>TN002: 영구 개체 데이터 형식
이 노트 파일에 저장 될 때 영구 c + + 개체와 개체 데이터의 형식을 지 원하는 MFC 루틴을 설명 합니다. 이 클래스에만 적용 됩니다는 [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로입니다.  
  
## <a name="the-problem"></a>문제  
 영구 데이터에 대 한 MFC 구현 파일의 단일 인접 부분에 많은 개체에 대 한 데이터를 저장합니다. 개체의 `Serialize` 메서드 compact 이진 형식으로 개체의 데이터를 변환 합니다.  
  
 구현 하면 사용 하 여 모든 데이터를 같은 형식으로 저장 된 [CArchive 클래스](../mfc/reference/carchive-class.md)합니다. 사용 하 여 한 `CArchive` 는 변환기 개체입니다. 이 개체를 호출 하기 전에 만든 시간에서 지속 되 면 [CArchive::Close](../mfc/reference/carchive-class.md#close)합니다. 이 메서드는 소멸자에서 프로그래머가 통해 명시적으로 또는 암시적으로 포함 하는 범위 종료 된 프로그램은 `CArchive`합니다.  
  
 이 노트 구현에 설명 된 `CArchive` 멤버 [CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject) 및 [CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject)합니다. Arcobj.cpp, 및에 대 한 주요 구현에서 이러한 함수에 대 한 코드를 찾을 수 있습니다 `CArchive` Arccore.cpp에 있습니다. 사용자 코드를 호출 하지 않는 `ReadObject` 및 `WriteObject` 직접 합니다. 클래스 관련 형식 안전 삽입 및 추출 연산자에 의해 자동으로 생성 되는 이러한 개체를 사용 하는 대신,는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로입니다. 다음 코드 방법을 `WriteObject` 및 `ReadObject` 암시적으로 호출 됩니다.  
  
```  
class CMyObject : public CObject  
{  
    DECLARE_SERIAL(CMyObject) 
};  
 
IMPLEMENT_SERIAL(CMyObj, CObject, 1)  
 
// example usage (ar is a CArchive&)  
CMyObject* pObj;  
CArchive& ar;  
ar <<pObj;        // calls ar.WriteObject(pObj)  
ar>> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))  
```  
  
## <a name="saving-objects-to-the-store-carchivewriteobject"></a>개체 (CArchive::WriteObject) 저장소에 저장  
 메서드가 `CArchive::WriteObject` 개체를 다시 생성 하는 데 사용 되는 헤더 데이터를 씁니다. 이 데이터는 두 부분으로 구성 됩니다: 개체 유형과 개체의 상태입니다. 또한이 메서드는 해당 개체 (순환 포인터 포함)에 대 한 포인터의 수에 관계 없이 단일 복사본만 저장 되도록 작성 되 고, 개체의 id를 유지 관리에 대 한 합니다.  
  
 (삽입)를 저장 하며 여러 "매니페스트 상수입니다."는 (압축 풀기) 개체를 복원 다음은 이진 파일에 저장 되 고 (참고 "w" 접두사는 16 비트 수량을 나타냅니다) 보관 하는 중요 한 정보를 제공 하는 값입니다.  
  
|태그|설명|  
|---------|-----------------|  
|wNullTag|NULL 개체 포인터 (0)에 사용 합니다.|  
|wNewClassTag|이 보관 컨텍스트 (-1) 새 뒤에 오는 클래스 설명을 나타냅니다.|  
|wOldClassTag|읽는 중인 개체의 클래스 (0x8000)이 컨텍스트에서 나타났습니다 나타냅니다.|  
  
 개체를 저장 하는 경우 아카이브를 유지 관리는 [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) (의 `m_pStoreMap`) 저장 된 개체에서 32 비트 영구 id (PID)로 매핑 인 합니다. 보관 파일의 상황에 맞는 저장 되는 모든 고유 클래스 이름과 모든 고유한 개체에 할당 됩니다. 이러한 Pid는 1에서 시작 하는 순차적으로 전달 됩니다. 이러한 Pid 보관 파일의 범위 외부에 의미가 없습니다 되며, 특히, 레코드 번호 또는 기타 identity 항목과 함께 다름.  
  
 에 `CArchive` 클래스, Pid는 32 비트 되지만 작성 16 비트로 0x7FFE 보다 큰 경우. 큰 Pid는 0x7FFF 뒤에 32 비트 PID로 기록 됩니다. 이전 버전에서 생성 된 프로젝트와의 호환성을 유지 합니다.  
  
 에 (일반적으로 전역 삽입 연산자 사용)에서 보관 파일에 개체를 저장 하는 요청이 수행 될 때 검사가 수행 되는 NULL에 대 한 [CObject](../mfc/reference/cobject-class.md) 포인터입니다. 포인터가 NULL 인 경우는 `wNullTag` 보관 스트림이에 삽입 됩니다.  
  
 포인터가 NULL이 아닌 사용 하는지를 확인 하 고 serialize 할 수 있습니다 (클래스는는 `DECLARE_SERIAL` 클래스), 코드 검사는 `m_pStoreMap` 개체가 이미 저장 되어 있는지 여부를 확인 하려면. 있는 경우, 코드 보관 스트림으로 해당 개체와 연결 된 32 비트 PID를 삽입 합니다.  
  
 이전에 개체를 저장 하지 않은 경우 두 가지 가능성이 고려해 야 할: 개체와 개체의 정확한 유형 (즉, 클래스)이 보관 컨텍스트에 새 않거나 개체를 이미 확인 정확한 형식입니다. 형식을 볼 되어 있는지 여부를 확인 하려면 코드 쿼리는 `m_pStoreMap` 에 대 한는 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 일치 하는 개체는 `CRuntimeClass` 저장 되는 개체와 연결 된 개체입니다. 일치 하는 경우 `WriteObject` 태그에 대 한 비트에 삽입 `OR` 의 `wOldClassTag` 와이 인덱스입니다. 경우는 `CRuntimeClass` 보관 컨텍스트에이 새로운 `WriteObject` 해당 클래스에 새 PID를 할당 하 고 앞에, 보관 저장소에 삽입 하는 `wNewClassTag` 값입니다.  
  
 이 클래스에 대 한 설명자를 사용 하 여 보관 된 삽입 한 다음는 `CRuntimeClass::Store` 메서드. `CRuntimeClass::Store` 클래스는 ASCII 텍스트 이름과 클래스 (아래 참조)의 스키마 번호를 삽입합니다. 참고 ASCII 텍스트 이름의 사용 응용 프로그램 전반에 보관 파일의 고유성을 보장 하지 않습니다. 따라서 데이터 파일 손상을 방지 하기 위해 태그 해야 있습니다. 클래스 정보를 삽입 하는 다음 보관 파일에 개체를 배치는 `m_pStoreMap` 를 호출 하 여 `Serialize` 클래스 관련 데이터를 삽입 하는 메서드. 개체에 배치 된 `m_pStoreMap` 호출 하기 전에 `Serialize` 개체의 여러 복사본을 저장소에 저장 되지 않도록 방지 합니다.  
  
 호출 해야 합니다 (일반적으로 네트워크 개체의 루트)에서 초기 호출자에 반환할 때 [CArchive::Close](../mfc/reference/carchive-class.md#close)합니다. 다른 수행 하려는 경우 [CFile](../mfc/reference/cfile-class.md)호출 해야 작업을는 `CArchive` 메서드 [플러시](../mfc/reference/carchive-class.md#flush) 보관 파일의 손상을 방지 하려면.  
  
> [!NOTE]
>  이 구현에서는 보관 컨텍스트 당 0x3FFFFFFE 인덱스의 하드 제한입니다. 이 숫자 고유 개체 및 클래스는 단일 보관 파일에 저장할 수 있는 최대 수를 나타내지만 단일 디스크 파일을 보관 컨텍스트 개수는 제한이 있을 수 있습니다.  
  
## <a name="loading-objects-from-the-store-carchivereadobject"></a>저장소 (CArchive::ReadObject)에서 개체를 로드합니다.  
 사용 하 여 개체 (압축 풀기) 로드 하는 `CArchive::ReadObject` 메서드는 반대로 이며 `WriteObject`합니다. 와 마찬가지로 `WriteObject`, `ReadObject` 사용자 코드;가 직접 호출할 수 없는 사용자 코드를 호출 하는 형식이 안전한 추출 연산자를 호출 해야 `ReadObject` 에서 정상적인 `CRuntimeClass`합니다. 이렇게 하면 추출 작업의 형식 무결성.  
  
 이후는 `WriteObject` 구현 할당 증가 Pid가 1부터 시작 (0 NULL 개체로 미리 정의 됨)는 `ReadObject` 구현 보관 컨텍스트 상태를 유지 하 여 배열을 사용할 수 있습니다. PID의 현재 상한 보다 큰 경우 PID를 저장소에서 읽을 하는 때는 `m_pLoadArray`, `ReadObject` 새 개체 (또는 클래스 설명) 따르는지를 알고 있습니다.  
  
## <a name="schema-numbers"></a>스키마 번호  
 클래스에 할당 하는 스키마 번호인 경우는 `IMPLEMENT_SERIAL` 클래스의 메서드 발생, "버전" 클래스 구현입니다. 스키마는 클래스의 구현, 하지 횟수를 지정된 된 개체 이루어졌을 영구 (일반적으로 개체 버전 이라고 함).  
  
 시간이 지남에 따라 동일한 클래스의 여러 다른 구현을 유지 하려는 경우 스키마 개체의 수정 하는 대로 증가 `Serialize` 메서드 구현을 사용 하면 이전 버전의를 사용 하 여 저장 된 개체를 로드할 수 있는 코드를 작성할 수 있습니다 구현입니다.  
  
 `CArchive::ReadObject` 메서드는 throw 한 [CArchiveException](../mfc/reference/carchiveexception-class.md) 메모리에 있는 클래스 설명 스키마 수가 다른 영구 저장소에서 스키마 번호를 발견 하면 합니다. 이 예외에서 복구 하려면 쉽지 않습니다.  
  
 사용할 수 있습니다 `VERSIONABLE_SCHEMA` 와 결합 (비트 `OR`)이이 예외가 throw 되지 변경 하지 않으려면 스키마 버전입니다. 사용 하 여 `VERSIONABLE_SCHEMA`, 사용자 코드 적절 한 조치를 취할 수 있습니다는 `Serialize` 함수 반환 값을 확인 하 여 [CArchive::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema)합니다.  
  
## <a name="calling-serialize-directly"></a>호출 직접 Serialize  
 대부분의 경우 일반 개체 보관 체계의 오버 헤드 `WriteObject` 및 `ReadObject` 필요 하지 않습니다. 데이터를 직렬화 할 일반적인 경우는 [CDocument](../mfc/reference/cdocument-class.md)합니다. 이 경우에 `Serialize` 의 메서드는 `CDocument` 추출 또는 삽입 연산자가 있는 하지를 직접 호출 됩니다. 문서 내용을 보다 일반적인 개체 보관 체계를 사용 차례로 수 있습니다.  
  
 호출 `Serialize` 직접 다음과 같은 장점 및 단점에:  
  
-   없음 추가 바이트를 설정 하기 전에 보관 파일에 또는 개체가 serialize 되는 후에 추가 됩니다. 이 뿐만 아니라 저장된 된 데이터를 더 작은 하지만 구현할 수 있도록 `Serialize` 모두 처리할 수 있는 루틴 파일 형식입니다.  
  
-   MFC는 조정 하므로 `WriteObject` 및 `ReadObject` 구현과 관련된 컬렉션 연결 되지 것입니다 응용 프로그램에 보다 일반적인 개체 보관 체계 다른 용도로 필요한 경우가 아니면 합니다.  
  
-   코드는 이전 스키마 숫자에서 복구할 필요가 없습니다. 그러면 문서 serialization 코드를 인코딩 스키마 번호, 파일 형식 버전 번호 또는 있습니다 번호를 식별 하는 모든 데이터 파일의 시작 부분에 사용 합니다.  
  
-   직접 호출 하 여 serialize 되는 모든 개체 `Serialize` 사용해 서는 안 `CArchive::GetObjectSchema` 또는 해야 핸들 반환 값이-1 (단위)를 나타내는 있는지 버전 알 수 없습니다.  
  
 때문에 `Serialize` 라고 문서에서 직접 일반적으로 수 없으면 해당 부모 문서에 대 한 참조를 보관 하기 위해 문서 하위 개체에 대 한 합니다. 이러한 개체에 제공 해야 대 한 포인터는 컨테이너 문서 명시적으로 사용 해야 하거나 [CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject) 함수에 매핑하는 `CDocument` 이러한 백 포인터를 보관 하기 전에 PID에 대 한 포인터입니다.  
  
 앞에서 설명한 대로 버전 인코딩할 하 고 클래스 정보 직접 호출 하는 경우 해야 `Serialize` 를 직접 사용 하면 오래 된 파일과 함께 이전 버전과 호환성을 유지 하면서 형식은 나중에 변경할 수 있습니다. `CArchive::SerializeClass` 함수 직접 개체를 직렬화 또는 기본 클래스를 호출 하기 전에 명시적으로 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

