---
title: COleStreamFile 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
dev_langs:
- C++
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 805c32145d844cc1103cab7c4987c0595ff5935f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371392"
---
# <a name="colestreamfile-class"></a>COleStreamFile 클래스
데이터 스트림을 나타냅니다 ( `IStream`) OLE 구조적 저장소의 일부로 복합 파일입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|`COleStreamFile` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|스트림을 개체와 연결 합니다.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|전역 메모리에서 스트림을 만드는 개체에 연결 합니다.|  
|[COleStreamFile::CreateStream](#createstream)|스트림을 만들어지고 개체와 연결 됩니다.|  
|[COleStreamFile::Detach](#detach)|스트림을 개체에서 연결을 끊습니다.|  
|[COleStreamFile::GetStream](#getstream)|현재 스트림을 반환합니다.|  
|[COleStreamFile::OpenStream](#openstream)|안전 하 게 되는 스트림을 엽니다 하 고 개체와 연결 합니다.|  
  
## <a name="remarks"></a>설명  
 `IStorage` 열거나 메모리 스트림을 경우가 아니라면를 만들 수 있는 스트림 수 전에 개체가 존재 해야 합니다.  
  
 `COleStreamFile` 개체와 똑같이 조작 [CFile](../../mfc/reference/cfile-class.md) 개체입니다.  
  
 스트림 및 저장소를 조작 하는 방법에 대 한 자세한 내용은 문서 참조 [컨테이너: 복합 파일](../../mfc/containers-compound-files.md)...  
  
 자세한 내용은 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 및 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) Windows sdk에서입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="attach"></a>  COleStreamFile::Attach  
 사용 하 여 제공 된 OLE 스트림을 연결의 `COleStreamFile` 개체입니다.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStream`  
 OLE 스트림 가리키는 ( `IStream`) 개체와 연결 되도록 합니다. 일 수 없습니다 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 개체가 이미 아니어야 OLE 스트림와 연결 합니다.  
  
 자세한 내용은 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows sdk에서입니다.  
  
##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile  
 
          `COleStreamFile` 개체를 만듭니다.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStream`  
 개체와 연결 될 OLE 스트림에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 경우 `lpStream` 은 **NULL**, 개체가 OLE 스트림과 연결 된, 제공 된 OLE 스트림과 연결 된 개체가 그렇지 않은 경우.  
  
 자세한 내용은 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows sdk에서입니다.  
  
##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream  
 안전 하 게 오류는 일반, 예상 조건 공유, 글로벌 메모리 부족 새 스트림을 만듭니다.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pError`  
 가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 **NULL** 만들기 작업의 완료 상태를 나타내는입니다. 스트림을 만들기를 시도 하 여 생성 된 가능한 예외를 모니터링 하려는 경우이 매개 변수를 제공 합니다.  
  
### <a name="return-value"></a>반환 값  
 스트림이 성공적으로 만들어지면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 메모리 OLE 하위 시스템에 의해 할당 됩니다.  
  
 자세한 내용은 참조 [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) Windows sdk에서입니다.  
  
##  <a name="createstream"></a>  COleStreamFile::CreateStream  
 오류는 일반, 예상 조건 제공 되는 저장소 개체에 새 스트림을 안전 하 게 만듭니다.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStorage`  
 만들 스트림의 포함 하는 OLE 저장소 개체를 가리킵니다. 일 수 없습니다 **NULL**합니다.  
  
 `lpszStreamName`  
 만들 스트림의 이름입니다. 일 수 없습니다 **NULL**합니다.  
  
 `nOpenFlags`  
 스트림을 열 때 사용할 액세스 모드입니다. 전용, 읽기/쓰기가 가능 하며 모드 만들 기본적으로 사용 됩니다. 사용 가능한 모드의 전체 목록은 참조 하십시오. [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)합니다.  
  
 `pError`  
 가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 **NULL**합니다. 스트림을 만들기를 시도 하 여 생성 된 가능한 예외를 모니터링 하려는 경우이 매개 변수를 제공 합니다.  
  
### <a name="return-value"></a>반환 값  
 스트림이 성공적으로 만들어지면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 열기 작업이 실패 하는 경우 파일 예외가 throw 됩니다 및 `pError` 않습니다 **NULL**합니다.  
  
 자세한 내용은 참조 [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) Windows sdk에서입니다.  
  
##  <a name="detach"></a>  COleStreamFile::Detach  
 스트림을 닫지 않고 스트림을 개체에서 연결을 끊습니다.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>반환 값  
 스트림에 대 한 포인터 ( `IStream`)를이 개체와 연결 합니다.  
  
### <a name="remarks"></a>설명  
 스트림을은 프로그램을 종료 하기 전에 다른 방식으로 닫아야 합니다.  
  
 자세한 내용은 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows sdk에서입니다.  
  
##  <a name="getstream"></a>  COleStreamFile::GetStream  
 현재 스트림에 대 한 포인터를 반환 하려면이 함수를 호출 합니다.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 스트림 인터페이스에 대 한 포인터 ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="openstream"></a>  COleStreamFile::OpenStream  
 기존 스트림을 엽니다.  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStorage`  
 스트림을 열 수를 포함 하는 OLE 저장소 개체를 가리킵니다. 일 수 없습니다 **NULL**합니다.  
  
 `lpszStreamName`  
 열 스트림의 이름입니다. 일 수 없습니다 **NULL**합니다.  
  
 `nOpenFlags`  
 스트림을 열 때 사용할 액세스 모드입니다. 전용 및 읽기/쓰기 모드는 기본적으로 사용 됩니다. 사용 가능한 모드 목록은 전체 참조 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)합니다.  
  
 `pError`  
 가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 **NULL**합니다. 가능한 예외 스트림을 열을 모니터링 하려는 경우이 매개 변수를 제공 합니다.  
  
### <a name="return-value"></a>반환 값  
 스트림이 성공적으로 열릴 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 열기 작업이 실패 하는 경우 파일 예외가 throw 됩니다 및 `pError` 않습니다 **NULL**합니다.  
  
 자세한 내용은 참조 [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFile 클래스](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



