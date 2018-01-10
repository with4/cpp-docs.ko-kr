---
title: "CArchive 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArchive
- AFX/CArchive
- AFX/CArchive::CArchive
- AFX/CArchive::Abort
- AFX/CArchive::Close
- AFX/CArchive::Flush
- AFX/CArchive::GetFile
- AFX/CArchive::GetObjectSchema
- AFX/CArchive::IsBufferEmpty
- AFX/CArchive::IsLoading
- AFX/CArchive::IsStoring
- AFX/CArchive::MapObject
- AFX/CArchive::Read
- AFX/CArchive::ReadClass
- AFX/CArchive::ReadObject
- AFX/CArchive::ReadString
- AFX/CArchive::SerializeClass
- AFX/CArchive::SetLoadParams
- AFX/CArchive::SetObjectSchema
- AFX/CArchive::SetStoreParams
- AFX/CArchive::Write
- AFX/CArchive::WriteClass
- AFX/CArchive::WriteObject
- AFX/CArchive::WriteString
- AFX/CArchive::m_pDocument
dev_langs: C++
helpviewer_keywords:
- CArchive [MFC], CArchive
- CArchive [MFC], Abort
- CArchive [MFC], Close
- CArchive [MFC], Flush
- CArchive [MFC], GetFile
- CArchive [MFC], GetObjectSchema
- CArchive [MFC], IsBufferEmpty
- CArchive [MFC], IsLoading
- CArchive [MFC], IsStoring
- CArchive [MFC], MapObject
- CArchive [MFC], Read
- CArchive [MFC], ReadClass
- CArchive [MFC], ReadObject
- CArchive [MFC], ReadString
- CArchive [MFC], SerializeClass
- CArchive [MFC], SetLoadParams
- CArchive [MFC], SetObjectSchema
- CArchive [MFC], SetStoreParams
- CArchive [MFC], Write
- CArchive [MFC], WriteClass
- CArchive [MFC], WriteObject
- CArchive [MFC], WriteString
- CArchive [MFC], m_pDocument
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9cc94e78656c53156b8696b927780f46e939861a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="carchive-class"></a>CArchive 클래스
개체의 복잡 한 네트워크는 영구 이진 형식 (일반적으로 디스크 저장소)는 해당 개체를 삭제 한 후 계속 되 면에 저장할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CArchive  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CArchive::CArchive](#carchive)|
          `CArchive` 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CArchive::Abort](#abort)|예외를 throw 하지 않고 보관 파일을 닫습니다.|  
|[CArchive::Close](#close)|기록 되지 않은 데이터를 플러시하고에서 연결을 끊습니다는 `CFile`합니다.|  
|[CArchive::Flush](#flush)|보관 파일 버퍼의 기록 되지 않은 데이터를 지웁니다.|  
|[CArchive::GetFile](#getfile)|가져옵니다는 `CFile` 이 보관 파일에 대 한 개체 포인터입니다.|  
|[CArchive::GetObjectSchema](#getobjectschema)|호출 된 `Serialize` 역직렬화 하는 개체의 버전을 확인 하는 함수입니다.|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Windows 소켓 중 버퍼가 비어 있는지 여부를 결정 프로세스를 수신 합니다.|  
|[CArchive::IsLoading](#isloading)|아카이브를 로드 하는지 여부를 결정 합니다.|  
|[CArchive::IsStoring](#isstoring)|보관 파일에서 저장 하 고 있는지 여부를 결정 합니다.|  
|[CArchive::MapObject](#mapobject)|에 파일에 serialize 되지 않은 없지만 참조할 하위 개체에 사용할 수 있는 지도 개체를 배치 합니다.|  
|[CArchive::Read](#read)|원시 바이트를 읽습니다.|  
|[CArchive::ReadClass](#readclass)|클래스 참조와 함께 이전에 저장 하는 읽기 `WriteClass`합니다.|  
|[CArchive::ReadObject](#readobject)|개체의 호출 `Serialize` 로드를 위한 함수입니다.|  
|[CArchive::ReadString](#readstring)|한 줄 텍스트를 읽습니다.|  
|[CArchive::SerializeClass](#serializeclass)|에 대 한 클래스 참조를 씁니다는 `CArchive` 방향에 따라 개체는 `CArchive`합니다.|  
|[CArchive::SetLoadParams](#setloadparams)|부하 배열 증가 하는 크기를 설정 합니다. 모든 개체를 로드 하기 전에 또는 하기 전에 호출 해야 `MapObject` 또는 `ReadObject` 라고 합니다.|  
|[CArchive::SetObjectSchema](#setobjectschema)|보관 개체에 저장 된 개체 스키마를 설정 합니다.|  
|[CArchive::SetStoreParams](#setstoreparams)|해시 테이블 크기와 serialization 프로세스 중 고유 개체를 식별 하는 데 map의 블록 크기를 설정 합니다.|  
|[CArchive::Write](#write)|원시 바이트를 씁니다.|  
|[CArchive::WriteClass](#writeclass)|기록에 대 한 참조는 `CRuntimeClass` 에 `CArchive`합니다.|  
|[CArchive::WriteObject](#writeobject)|개체의 호출 `Serialize` 저장 하기 위한 함수입니다.|  
|[CArchive::WriteString](#writestring)|한 줄 텍스트를 씁니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CArchive::operator&lt;&lt;](#operator_lt_lt)|개체와 기본 형식을 보관 파일에 저장합니다.|  
|[CArchive::operator&gt;&gt;](#operator_gt_gt)|개체와 기본 형식을 보관 파일에서 로드합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CArchive::m_pDocument](#m_pdocument)||  
  
## <a name="remarks"></a>설명  
 `CArchive`기본 클래스는 없습니다.  
  
 나중에 개체 로드할 수 있습니다는 영구 저장소에서 메모리에 재구성을 합니다. 이 프로세스의 영구 데이터를 만드는 "serialization" 라고 합니다.  
  
 보관 개체 종류의 이진 스트림으로의 생각할 수 있습니다. 입/출력 스트림, 같은 보관 파일에 연결 되며 쓰기를 버퍼링된 하 고 저장소 간에 데이터를 읽을 수 합니다. 입/출력 스트림 ASCII 문자의 시퀀스를 처리 하지만 보관 효율적이 고 중복 되지 않은 형식의 이진 개체 데이터를 처리 합니다.  
  
 만들어야는 [CFile](../../mfc/reference/cfile-class.md) 개체 만들기 전에 `CArchive` 개체입니다. 또한 보관 파일의 로드/저장 상태 파일의 열기 모드와 호환 되는지 확인 해야 합니다. 파일당 하나의 활성 보관 제한 됩니다.  
  
 생성할 때는 `CArchive` 개체 클래스의 개체에 연결할 `CFile` (또는 파생된 클래스) 열려 있는 파일을 나타내는입니다. 또한 보관 파일을 로드 하거나 저장을 사용할지를 지정 합니다. A `CArchive` 기본 형식 뿐만 아니라 개체의 개체를 처리할 수 [CObject](../../mfc/reference/cobject-class.md)-파생 된 클래스 serialization을 위해 설계 되었습니다. Serializable 클래스는 일반적으로 `Serialize` 멤버 함수 이므로 일반적으로 사용 하 여는 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로, 클래스 아래에 설명 된 대로 `CObject`합니다.  
  
 오버 로드 된 추출 (  **>>** ) 및 삽입 (  **<<** ) 연산자는 기본 유형을 모두 지 원하는 프로그래밍 인터페이스를 편리 하 게 보관 하 고 `CObject` -파생 된 클래스입니다.  
  
 `CArchive`또한 MFC Windows 소켓 클래스를 사용 하 여 프로그래밍을 지원 [CSocket](../../mfc/reference/csocket-class.md) 및 [CSocketFile](../../mfc/reference/csocketfile-class.md)합니다. [IsBufferEmpty](#isbufferempty) 멤버 함수는 해당 사용을 지원 합니다.  
  
 대 한 자세한 내용은 `CArchive`, 문서를 참조 [Serialization](../../mfc/serialization-in-mfc.md) 및 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CArchive`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="abort"></a>CArchive::Abort  
 예외를 throw 하지 않고 보관 파일을 닫으려면이 함수를 호출 합니다.  
  
```  
void Abort ();
```  
  
### <a name="remarks"></a>설명  
 **CArchive** 소멸자는 정상적으로 호출 **닫기**, 모든 데이터를 저장 하지 않은 플러시합니다를 연결 된 `CFile` 개체입니다. 이 예외가 발생할 수 있습니다.  
  
 이러한 예외를 catch 하는 경우는 것이 좋습니다 사용할 **중단**destructing 되도록는 `CArchive` 개체 추가 예외가 발생 하지 않습니다. 예외 처리 때 `CArchive::Abort` 때문에 오류에 예외를 throw 하지 것입니다 달리 [CArchive::Close](#close), **중단** 오류를 무시 합니다.  
  
 사용 하는 경우 **새** 할당 하는 `CArchive` 힙에 개체 파일을 닫은 후에 삭제 해야 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CArchive::WriteClass](#writeclass)합니다.  
  
##  <a name="carchive"></a>CArchive::CArchive  
 생성 된 `CArchive` 개체를 로드 하거나 개체를 저장 하기 위해 사용할 됩니다 있는지 여부를 지정 합니다.  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFile`  
 에 대 한 포인터는 `CFile` 백과 또는 영구 데이터의 대상 개체입니다.  
  
 `nMode`  
 개체에서 로드 되거나 보관 파일에 저장 될 지 여부를 지정 하는 플래그입니다. `nMode` 매개 변수는 다음 값 중 하나가 있어야 합니다.  
  
- **CArchive::load** 보관 파일에서 데이터를 로드 합니다. 하기만 `CFile` 읽기 권한이 있습니다.  
  
- **CArchive::store** 보관 파일에 데이터를 저장 합니다. 필요 `CFile` 쓰기 권한입니다.  
  
- **CArchive::bNoFlushOnDelete** 보관 파일에서 자동으로 호출 되지 않도록 `Flush` 보관 소멸자가 호출 되는 경우. 명시적으로 호출 하는 일을 담당 하는 경우이 플래그를 설정 하면 **닫기** 소멸자가 호출 되기 전에 합니다. 이렇게 하지 않으면 데이터가 손상 됩니다.  
  
 `nBufSize`  
 내부 파일 버퍼의 크기를 바이트 단위로 지정 하는 정수입니다. 참고 기본 버퍼 크기는 4, 096 바이트입니다. 큰 개체를 정기적으로 보관 하는 경우 더 큰 버퍼 크기는 파일 버퍼 크기의 배수를 사용 하는 경우 성능이 향상 됩니다.  
  
 `lpBuf`  
 사용자가 제공한 버퍼의 크기에 대 한 선택적 포인터 `nBufSize`합니다. 이 매개 변수를 지정 하지 않으면 보관은 로컬 힙에서 버퍼 할당 하 고는 개체가 소멸 될 때이 해제 합니다. 보관 파일에서 사용자가 제공한 버퍼를 해제 하지 않습니다.  
  
### <a name="remarks"></a>설명  
 보관 파일을 만든 후에이 사양을 변경할 수 없습니다.  
  
 사용할 수 없습니다 `CFile` 아카이브 종료 될 때까지 파일의 상태를 변경 하는 작업입니다. 이러한 작업의 보관 파일의 무결성을 손상 됩니다. 보관 파일의 파일 개체를 가져오는 방법으로 파일 포인터의 위치를 직렬화 하는 동안 언제 든 액세스할 수 있습니다는 [GetFile](#getfile) 멤버 함수는 다음 사용 하 고는 [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) 함수 . 호출 해야 [CArchive::Flush](#flush) 파일 포인터의 위치를 얻기 전에 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="close"></a>CArchive::Close  
 버퍼에에서 남아 있는 모든 데이터를 플러시하고, 보관 저장소를 닫습니다는 보관 파일에서 연결을 끊습니다.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>설명  
 보관 파일에 더 이상 작업이 허용 됩니다. 보관 파일을 닫은 후에 동일한 파일에 대 한 다른 보관을 만들 수 있습니다 또는 파일을 닫을 수 있습니다.  
  
 멤버 함수 **닫기** 모든 데이터가 파일에 보관 파일에서 전송 되어 있는지와 보관 사용할 수 없습니다. 파일에서 전송 하기 위해서는 저장 매체를 완료 하려면 먼저 사용 해야 [CFile::Close](../../mfc/reference/cfile-class.md#close) 를 삭제 합니다는 `CFile` 개체입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CArchive::WriteString](#writestring)합니다.  
  
##  <a name="flush"></a>CArchive::Flush  
 파일에 쓰여지도록 보관 버퍼에에서 남아 있는 모든 데이터를 강제로 수행 합니다.  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>설명  
 멤버 함수 `Flush` 파일에 모든 데이터가 보관 파일에서 전송 되는지 확인 합니다. 호출 해야 [CFile::Close](../../mfc/reference/cfile-class.md#close) 저장소 미디어에는 파일 전송을 완료할 수 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="getfile"></a>CArchive::GetFile  
 가져옵니다는 `CFile` 이 보관 파일에 대 한 개체 포인터입니다.  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 상수 포인터는 `CFile` 개체를 사용에서 합니다.  
  
### <a name="remarks"></a>설명  
 보관을 사용 하기 전에 플러시해야 `GetFile`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="getobjectschema"></a>CArchive::GetObjectSchema  
 이 함수 호출의 `Serialize` 현재 deserialize 중인 개체의 버전을 확인 하는 함수입니다.  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>반환 값  
 Deserialization 읽는 중인 개체의 버전 중  
  
### <a name="remarks"></a>설명  
 이 함수를 호출 인 유효한 경우에는 `CArchive` 개체 로드 되 고 ( [CArchive::IsLoading](#isloading) 0이 아닌 반환). 첫 번째 호출 이어야 합니다는 `Serialize` 함수 및 한 번만 호출된 합니다. 반환 값 ( **UINT**)-1, 버전 번호 알려진 하지 않음을 나타냅니다.  
  
 A `CObject`-파생된 클래스가 사용할 수 있습니다 **VERSIONABLE_SCHEMA** 결합 (비트를 사용 하 여 `OR`) 자체 스키마 버전 (에 `IMPLEMENT_SERIAL` 매크로)는 "블록인 개체를 만드는" 개체 즉, 해당 `Serialize` 멤버 함수는 여러 버전을 읽을 수 있습니다. 기본 프레임 워크 기능 (없이 **VERSIONABLE_SCHEMA**) 버전이 일치 하지 않을 때 예외를 throw 하는 것입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="isbufferempty"></a>CArchive::IsBufferEmpty  
 보관 개체의 내부 버퍼 비어 있는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>반환 값  
 보관 파일의 버퍼 비어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 MFC Windows 소켓 클래스를 사용 하 여 프로그래밍을 지원 하기 위해 제공 될 `CSocketFile`합니다. 와 연결 된 보관 파일에 사용할 필요가 없습니다는 `CFile` 개체입니다.  
  
 사용 하기 위한 이유 `IsBufferEmpty` 연관 된 보관으로는 `CSocketFile` 개체는 둘 이상의 메시지 또는 레코드 보관 파일의 버퍼 포함 될 수 있습니다. 하나의 메시지를 받은 후 사용 해야 `IsBufferEmpty` 계속는 버퍼가 비어 있을 때까지 데이터를 수신 하는 루프를 제어할 수 있습니다. 자세한 내용은 참조는 [수신](../../mfc/reference/casyncsocket-class.md#receive) 클래스의 멤버 함수 `CAsyncSocket`를 사용 하는 방법을 보여 주는 `IsBufferEmpty`합니다.  
  
 자세한 내용은 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
##  <a name="isloading"></a>CArchive::IsLoading  
 보관 된 데이터를 로드 하 고 있는지 여부를 결정 합니다.  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>반환 값  
 보관 저장소 로드;에 대 한 현재 사용 중인 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수 호출 됩니다는 `Serialize` 보관 된 클래스의 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="isstoring"></a>CArchive::IsStoring  
 보관 파일에서 데이터를 저장 하는지 여부를 결정 합니다.  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>반환 값  
 아카이브; 저장 하기 위해 현재 사용 중인 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수 호출 됩니다는 `Serialize` 보관 된 클래스의 함수입니다.  
  
 경우는 `IsStoring` 보관 파일의 상태 값은 0의 다음 `IsLoading` status = 0, 그 반대의 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="mapobject"></a>CArchive::MapObject  
 파일을 실제로 serialize 되지 않은 없지만 참조할 하위 개체에 사용할 수 있는 지도에 개체를 저장 하려면이 함수를 호출 합니다.  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>매개 변수  
 `pOb`  
 저장 되는 개체에 대 한 상수 포인터입니다.  
  
### <a name="remarks"></a>설명  
 예를 들어 문서를 serialize 하지 수 있지만 문서의 일부인 항목을 serialize 합니다. 호출 하 여 `MapObject`, 해당 항목 또는 하위 문서를 참조 하도록 허용 합니다. Serialize 된 하위 항목의 serialize 할 수는 또한 자신의 `m_pDocument` 후방 포인터입니다.  
  
 호출할 수 있습니다 `MapObject` 를 저장 하 고 로드는 `CArchive` 개체입니다. `MapObject`지정된 된 개체에서 유지 관리 하는 내부 데이터 구조에 추가 `CArchive` 개체 serialization 및 deserialization을 수행 하는 동안 하지만 달리 [ReadObject](#readobject) 및 [WriteObject](#writeobject) **,** 호출 하지 않는 개체에 serialize 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="m_pdocument"></a>CArchive::m_pDocument  
 로 설정 **NULL** 기본적으로이에 대 한이 포인터는 **CDocument** 의 사용자 이외의 값으로 설정할 수는 `CArchive` 려 인스턴스.  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>설명  
 이 포인터는 일반적으로 사용 serialization 프로세스를 serialize 하 고 모든 개체에 대 한 추가 정보를 전달 하는 합니다. 이 문서를 사용 하 여 포인터를 초기화 하 여 수행 (한 **CDocument**-파생 클래스) 하는 serialize 되 고, 필요한 경우 문서 내에서 개체는 문서에 액세스할 수 있도록 하는 방식에서입니다. 이 포인터는 또한 사용 `COleClientItem` serialization 동안에 개체입니다.  
  
 프레임 워크 집합 `m_pDocument` 에 사용자 파일을 실행 하면 serialize 하 고 문서 열기 또는 저장 명령입니다. 명시적으로 설정 해야 개체 연결 및 OLE 컨테이너 문서의 파일 열기 또는 저장 이외의 이유로 serialize 하는 경우 `m_pDocument`합니다. 예를 들어 이렇게 클립보드로 컨테이너 문서를 직렬화 할 때입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]  
  
##  <a name="operator_lt_lt"></a>CArchive::operator&lt;&lt;  
 표시 된 개체 또는 기본 형식 보관 파일에 저장합니다.  
  
```  
friend CArchive& operator<<(
    CArchive& ar,  
    const CObject* pOb);

 
throw(
    CArchiveException*, 
    CFileException*);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator<<(
    const ATL::CStringT<BaseType,  
    StringTraits>& str);  
  
CArchive& operator<<(BYTE by); 
CArchive& operator<<(WORD w); 
CArchive& operator<<(LONG l); 
CArchive& operator<<(DWORD dw); 
CArchive& operator<<(float f); 
CArchive& operator<<(double d); 
CArchive& operator<<(int i); 
CArchive& operator<<(short w); 
CArchive& operator<<(char ch); 
CArchive& operator<<(wchar_t ch); 
CArchive& operator<<(unsigned u); 
CArchive& operator<<(bool b); 
CArchive& operator<<(ULONGLONG dwdw); 
CArchive& operator<<(LONGLONG dwdw);
```  
  
### <a name="return-value"></a>반환 값  
 A `CArchive` 을 한 줄에 여러 명의 삽입 연산자를 사용 하면 참조 합니다.  
  
### <a name="remarks"></a>설명  
 위의 마지막 두 버전은 64 비트 정수를 저장 하기 위해.  
  
 사용 하는 경우는 `IMPLEMENT_SERIAL` 클래스 구현에 다음에 대 한 오버 로드 된 삽입 연산자에서 매크로 `CObject` 호출 하 여 보호 된 **WriteObject**합니다. 이 함수를 호출 하 여 `Serialize` 클래스의 함수입니다.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 삽입 연산자 (<<) 진단 덤핑 및 보관 파일에 저장을 지원 합니다.  
  
### <a name="example"></a>예  
 사용을 보여 주는이 예제는 `CArchive` 삽입 연산자 <<와 `int` 및 `long` 형식입니다.  
  
 [!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>예  
 이 예에서는 2의 사용법을 보여줍니다는 `CArchive` 삽입 연산자 <<와 `CStringT` 유형입니다.  
  
 [!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]  
  
##  <a name="operator_gt_gt"></a>CArchive::operator&gt;&gt;  
 표시 된 개체 또는 기본 형식 보관 파일에서 로드합니다.  
  
```  
friend CArchive& operator>>(
    CArchive& ar,  
    CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
friend CArchive& operator>>(
    CArchive& ar,  
    const CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator>>(
    ATL::CStringT<BaseType, 
    StringTraits>& str);  
  
CArchive& operator>>(BYTE& by);    
CArchive& operator>>(WORD& w);    
CArchive& operator>>(int& i);    
CArchive& operator>>(LONG& l);    
CArchive& operator>>(DWORD& dw);    
CArchive& operator>>(float& f);    
CArchive& operator>>(double& d);    
CArchive& operator>>(short& w);    
CArchive& operator>>(char& ch);    
CArchive& operator>>(wchar_t& ch);    
CArchive& operator>>(unsigned& u);    
CArchive& operator>>(bool& b);    
CArchive& operator>>(ULONGLONG& dwdw);   
CArchive& operator>>(LONGLONG& dwdw);
```  
  
### <a name="return-value"></a>반환 값  
 A `CArchive` 을 한 줄에 여러 명의 추출 연산자를 사용 하면 참조 합니다.  
  
### <a name="remarks"></a>설명  
 위의 마지막 두 버전 특히 64 비트 정수 로드 됩니다.  
  
 사용 하는 경우는 `IMPLEMENT_SERIAL` 클래스 구현에 한 추출 연산자에 대 한 오버 로드 된 후 매크로 `CObject` 호출 하 여 보호 된 **ReadObject** 함수 (0이 아닌 런타임 클래스 포인터로). 이 함수를 호출 하 여 `Serialize` 클래스의 함수입니다.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 추출 연산자 (>>) 보관 파일에서 로드를 지원 합니다.  
  
### <a name="example"></a>예  
 사용을 보여 주는이 예제는 `CArchive` 추출 연산자 >>와 `int` 유형입니다.  
  
 [!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>예  
 사용을 보여 주는이 예제는 `CArchive` 삽입 및 추출 연산자 <\< 및 >>와 `CStringT` 유형입니다.  
  
 [!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="read"></a>CArchive::Read  
 보관 파일에서 지정 된 바이트 수를 읽습니다.  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 보관 파일에서 읽은 데이터를 수신 하는 사용자가 제공한 버퍼에 대 한 포인터입니다.  
  
 `nMax`  
 부호 없는 정수로 바이트 수를 지정 하는 보관 파일에서 읽을 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 실제로 읽는 바이트 수를 포함 하는 부호 없는 정수입니다. 반환 값을 사용 하면 요청 된 수보다 작으면, 파일의 끝에 도달 했습니다. 파일 끝에 예외가 throw 됩니다.  
  
### <a name="remarks"></a>설명  
 보관 파일 바이트 해석 하지는 않습니다.  
  
 사용할 수는 **읽기** 내에서 멤버 함수에 `Serialize` 사용자 개체에 포함 된 일반 구조를 읽기 위한 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="readclass"></a>CArchive::ReadClass  
 이 멤버 함수를 함께 이전에 저장 하는 클래스에 대 한 참조를 읽을 호출 [WriteClass](#writeclass)합니다.  
  
```  
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,  
    UINT* pSchema = NULL,  
    DWORD* pObTag = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pClassRefRequested`  
 에 대 한 포인터는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 요청한 클래스 참조에 해당 합니다. 수 **NULL**합니다.  
  
 `pSchema`  
 이전에 저장 하는 런타임 클래스의 스키마에 대 한 포인터입니다.  
  
 `pObTag`  
 개체의 고유 태그를 참조 하는 수입니다. 구현에서 내부적으로 사용 [ReadObject](#readobject)합니다. 고급 프로그래밍만;에 대 한 노출 `pObTag` 해야 정상적으로 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조입니다.  
  
### <a name="remarks"></a>설명  
 경우 `pClassRefRequested` 않습니다 **NULL**, `ReadClass` 보관 된 클래스 정보 런타임 클래스와 호환 되는지 확인 합니다. 호환 되지 않는 경우 `ReadClass` throw 됩니다는 [CArchiveException](../../mfc/reference/carchiveexception-class.md)합니다.  
  
 런타임 클래스를 사용 해야 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial), 그렇지 않으면 `ReadClass` throw 됩니다는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.  
  
 경우 `pSchema` 은 **NULL**를 호출 하 여 저장 된 클래스의 스키마를 검색할 수 있습니다 [CArchive::GetObjectSchema](#getobjectschema), 그렇지 않으면  **\***  `pSchema`이전 저장 된 런타임 클래스의 스키마에 포함 됩니다.  
  
 사용할 수 있습니다 [SerializeClass](#serializeclass) 대신 `ReadClass`, 읽기와 쓰기 클래스 참조의 처리 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CArchive::WriteClass](#writeclass)합니다.  
  
##  <a name="readobject"></a>CArchive::ReadObject  
 보관 파일에서 개체 데이터를 읽고 적절 한 형식의 개체를 생성 합니다.  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>매개 변수  
 `pClass`  
 에 대 한 상수 포인터는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 읽을 하려는 개체에 해당 합니다.  
  
### <a name="return-value"></a>반환 값  
 A [CObject](../../mfc/reference/cobject-class.md) 올바른 안전 하 게 캐스팅 해야 하는 포인터를 사용 하 여 클래스를 파생 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 호출 됩니다는 `CArchive` 추출 (  **>>** )에 대 한 연산자는 오버 로드는 [CObject](../../mfc/reference/cobject-class.md) 포인터입니다. **ReadObject**를 호출 하는 `Serialize` 보관 된 클래스의 함수입니다.  
  
 0이 아닌 제공 하는 경우 `pClass` 으로 얻을 수 있는 매개 변수는 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로, 다음 함수는 보관 된 개체의 런타임 클래스를 확인 합니다. 사용한이 가정은 `IMPLEMENT_SERIAL` 클래스의 구현에서 매크로입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CArchive::WriteObject](#writeobject)합니다.  
  
##  <a name="readstring"></a>CArchive::ReadString  
 연결 된 파일에서 버퍼도 텍스트 데이터를 읽어이 멤버 함수 호출의 `CArchive` 개체입니다.  
  
```  
BOOL ReadString(CString& rString); 
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `rString`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) CArchive 개체와 연결 된 파일에서 읽은 후 결과 문자열을 포함 하는 합니다.  
  
 `lpsz`  
 사용자가 제공한 버퍼를 null로 끝나는 텍스트 문자열을 받게 됩니다에 대 한 포인터를 지정 합니다.  
  
 `nMax`  
 읽을 문자 최대 수를 지정 합니다. 하나 여야 함의 크기 보다 작은 *lpsz* 버퍼입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 하는 버전에서 **BOOL**, **TRUE** 성공 하면 **FALSE** 그렇지 않은 경우.  
  
 반환 하는 버전에는 `LPTSTR`에서 텍스트 데이터를 포함 하는 버퍼에 대 한 포인터 **NULL** 경우 파일 끝에 도달 했습니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수를의 버전에는 `nMax` 매개 변수 버퍼는 보류 된 제한 `nMax` -1 문자입니다. 읽기는 캐리지 리턴-줄 바꿈 쌍으로 중지 됩니다. 후행 줄 바꿈 문자는 항상 제거 됩니다. Null 문자 ('\0')는 두 경우 모두 추가 됩니다.  
  
 [CArchive::Read](#read) 캐리지 리턴-줄 바꿈 쌍에 텍스트 모드 입력 하지만 종료 되지 않는 제공 됩니다.  
  
### <a name="example"></a>예  
  예를 참조 [CArchive::WriteString](#writestring)합니다.  
  
##  <a name="serializeclass"></a>CArchive::SerializeClass  
 저장 하 고 기본 클래스의 버전 정보를 로드 하려는 경우이 함수를 호출 합니다.  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>매개 변수  
 `pClassRef`  
 기본 클래스에 대 한 런타임 클래스 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `SerializeClass`에 대 한 클래스에 대 한 참조를 씁니다는 `CArchive` 방향에 따라 개체는 `CArchive`합니다. 사용 하 여 `SerializeClass` 대신 [ReadClass](#readclass) 및 [WriteClass](#writeclass) 기본 클래스 개체를 serialize 하는 편리한 방법으로 `SerializeClass` 더 적은 코드 및 매개 변수도 필요 합니다.  
  
 마찬가지로 `ReadClass`, `SerializeClass` 보관 된 클래스 정보 런타임 클래스와 호환 되는지 확인 합니다. 호환 되지 않는 경우 `SerializeClass` throw 됩니다는 [CArchiveException](../../mfc/reference/carchiveexception-class.md)합니다.  
  
 런타임 클래스를 사용 해야 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial), 그렇지 않으면 `SerializeClass` throw 됩니다는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.  
  
 사용 하 여는 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로 대 한 값을 검색 하는 `pRuntimeClass` 매개 변수입니다. 기본 클래스 사용 해야 합니다는 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="setloadparams"></a>CArchive::SetLoadParams  
 호출 `SetLoadParams` 많은 수의 읽을 하려는 경우 `CObject`-보관에서 파생 되는 개체입니다.  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>매개 변수  
 `nGrowBy`  
 최소 크기 증가 사용 하는 필요한 경우 할당할 슬롯 요소 수입니다.  
  
### <a name="remarks"></a>설명  
 `CArchive`부하 배열을 사용 하 여 보관 파일에 저장 된 개체에 대 한 참조를 확인 합니다. `SetLoadParams`부하 배열 증가 하는 크기를 설정할 수 있습니다.  
  
 호출 해서는 안 `SetLoadParams` 모든 개체를 로드 한 후 또는 이후에 [MapObject](#mapobject) 또는 [ReadObject](#readobject) 호출 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="setobjectschema"></a>CArchive::SetObjectSchema  
 보관 개체에 저장 된 개체 스키마를 설정 하려면이 함수를 호출 `nSchema`합니다.  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>매개 변수  
 `nSchema`  
 개체의 스키마를 지정합니다.  
  
### <a name="remarks"></a>설명  
 다음 호출 [GetObjectSchema](#getobjectschema) 에 저장 된 값을 반환 합니다 `nSchema`합니다.  
  
 사용 하 여 `SetObjectSchema` 고급 버전 관리;에 대 한 예를 들어 경우 강제 적용 하려는 특정 버전에서 읽을 수는 `Serialize` 파생된 클래스의 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="setstoreparams"></a>CArchive::SetStoreParams  
 사용 하 여 `SetStoreParams` 많은 수의 저장할 때 `CObject`-파생 개체를 보관에서 합니다.  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>매개 변수  
 *nHashSize*  
 인터페이스 포인터의 해시 테이블의 크기에 매핑합니다. 최적 값을 지정 해야 합니다.  
  
 `nBlockSize`  
 매개 변수를 확장 하기 위한 메모리 할당 세분성을 지정 합니다. 최상의 성능을 위해 2의 거듭제곱 이어야 합니다.  
  
### <a name="remarks"></a>설명  
 `SetStoreParams`해시 테이블 크기와 serialization 프로세스 중 고유 개체를 식별 하는 데 map의 블록 크기를 설정할 수 있습니다.  
  
 호출 해서는 안 `SetStoreParams` 개체가 저장 된 후 또는 이후에 [MapObject](#mapobject) 또는 [WriteObject](#writeobject) 호출 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="write"></a>CArchive::Write  
 보관 파일에 지정된 된 수의 바이트를 씁니다.  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 보관 파일에 쓸 데이터를 포함 하는 사용자가 제공한 버퍼에 대 한 포인터입니다.  
  
 `nMax`  
 보관 파일에 쓸 바이트 수를 지정 하는 정수입니다.  
  
### <a name="remarks"></a>설명  
 보관 파일에서 바이트를 포맷 되지 않습니다.  
  
 사용할 수 있습니다는 **쓰기** 멤버 함수 내에서 프로그램 `Serialize` 일반 구조를 작성 하는 함수 개체에 포함 되어 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="writeclass"></a>CArchive::WriteClass  
 사용 하 여 `WriteClass` 파생된 클래스의 serialization 동안 기본 클래스의 버전 및 클래스 정보를 저장 합니다.  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>매개 변수  
 `pClassRef`  
 에 대 한 포인터는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 요청한 클래스 참조에 해당 합니다.  
  
### <a name="remarks"></a>설명  
 `WriteClass`기록에 대 한 참조는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 를 기본 클래스에 대 한는 `CArchive`합니다. 사용 하 여 [CArchive::ReadClass](#readclass) 에 참조를 검색 합니다.  
  
 `WriteClass`보관 된 클래스 정보 런타임 클래스와 호환 되는지 확인 합니다. 호환 되지 않는 경우 `WriteClass` throw 됩니다는 [CArchiveException](../../mfc/reference/carchiveexception-class.md)합니다.  
  
 런타임 클래스를 사용 해야 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial), 그렇지 않으면 `WriteClass` throw 됩니다는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.  
  
 사용할 수 있습니다 [SerializeClass](#serializeclass) 대신 `WriteClass`, 읽기와 쓰기 클래스 참조의 처리 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]  
  
##  <a name="writeobject"></a>CArchive::WriteObject  
 지정 된 저장 `CObject` 보관 파일에 있습니다.  
  
```  
void WriteObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>매개 변수  
 `pOb`  
 저장 되는 개체에 대 한 상수 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 호출 됩니다는 `CArchive` 삽입 (  **<<** )에 대 한 연산자는 오버 로드 `CObject`합니다. **WriteObject**를 호출 하는 `Serialize` 보관 된 클래스의 함수입니다.  
  
 사용 해야 합니다는 `IMPLEMENT_SERIAL` 보관을 사용 하도록 설정 하는 매크로입니다. **WriteObject** 보관 파일에 ASCII 클래스 이름을 기록 합니다. 이 클래스 이름은 로드 프로세스 동안 나중에 유효성이 검사 됩니다. 특별 한 인코딩 체계에는 불필요 한 클래스의 여러 개체에 대 한 클래스 이름 중복이 되지 않습니다. 이 스키마 또한 하나 이상의 포인터의 대상이 되는 개체의 중복 저장소를 방지 합니다.  
  
 인코딩 (ASCII 클래스 이름의 존재 여부 포함) 방법 정확한 개체는 구현 정보 이며 변경 될 수 이후 버전의 라이브러리.  
  
> [!NOTE]
>  만들기, 삭제 및 보관 하기 전에 모든 개체 업데이트를 완료 합니다. 보관 개체 수정 하지 않고도 보관을 혼합 하면 손상 됩니다.  
  
### <a name="example"></a>예  
 클래스의 정의 대 한 `CAge`, 예를 참조 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist)합니다.  
  
 [!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="writestring"></a>CArchive::WriteString  
 이 멤버 함수를 사용 하 여 버퍼에서 데이터와 연결 된 파일에 쓰려고는 `CArchive` 개체입니다.  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpsz`  
 Null로 끝나는 텍스트 문자열을 포함 하는 버퍼에 대 한 포인터를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 종료 null 문자 ('\0'); 파일에 기록 되지 않습니다. 또는 줄 바꿈을 자동으로 기록 됩니다.  
  
 `WriteString`디스크 꽉 참 조건을 포함 하 여 여러 조건에 대 한 응답에 예외를 throw 합니다.  
  
 **쓰기** 사용할 수 있지만 null 문자를 종료 하는 대신 파일에 요청된 된 바이트 수가 기록 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFile 클래스](../../mfc/reference/cfile-class.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [CSocket 클래스](../../mfc/reference/csocket-class.md)   
 [CSocketFile 클래스](../../mfc/reference/csocketfile-class.md)
