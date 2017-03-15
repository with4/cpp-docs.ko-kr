---
title: "COleStreamFile 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleStreamFile
dev_langs:
- C++
helpviewer_keywords:
- data streams [C++]
- streams [C++], OLE
- data streams [C++], OLE
- structured storage in OLE
- OLE structured storage [C++]
- OLE [C++], streams of data
- COleStreamFile class
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0840d365f4179da0ad680256688eaf9484cb3cd8
ms.lasthandoff: 02/24/2017

---
# <a name="colestreamfile-class"></a>COleStreamFile 클래스
데이터의 스트림을 나타냅니다 ( `IStream`) OLE 구조적 저장소의 일부로 복합 파일입니다.  
  
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
|[COleStreamFile::Attach](#attach)|스트림 개체에 연결합니다.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|전역 메모리에서 스트림을 만들고 개체와 연결 합니다.|  
|[COleStreamFile::CreateStream](#createstream)|스트림을 만들고 개체와 연결 합니다.|  
|[COleStreamFile::Detach](#detach)|스트림을 개체에서 연결을 끊습니다.|  
|[COleStreamFile::GetStream](#getstream)|현재 스트림을 반환합니다.|  
|[COleStreamFile::OpenStream](#openstream)|스트림을 엽니다 안전 하 게 개체에 연결 합니다.|  
  
## <a name="remarks"></a>주의  
 `IStorage` 스트림 이름을 열거나 하지 않은 경우 메모리 스트림을 생성 전에 개체가 존재 해야 합니다.  
  
 `COleStreamFile`개체를 정확히 동일 하 게 조작 [CFile](../../mfc/reference/cfile-class.md) 개체입니다.  
  
 스트림 및 저장소를 조작 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [컨테이너: 복합 파일](../../mfc/containers-compound-files.md)...  
  
 자세한 내용은 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 및 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="a-nameattacha--colestreamfileattach"></a><a name="attach"></a>COleStreamFile::Attach  
 사용 하 여 제공 된 OLE 스트림을 연결의 `COleStreamFile` 개체입니다.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStream`  
 OLE 스트림 가리키는 ( `IStream`) 개체와 연결 되도록 합니다. 안 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 개체가 이미 아니어야 OLE 스트림과 사용 하 여 연결 합니다.  
  
 자세한 내용은 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namecolestreamfilea--colestreamfilecolestreamfile"></a><a name="colestreamfile"></a>COleStreamFile::COleStreamFile  
 
          `COleStreamFile` 개체를 만듭니다.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStream`  
 개체와 연결 되도록 OLE 스트림에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 경우 `lpStream` 는 **NULL**, 개체가 OLE 스트림과 연결 된, 제공 된 OLE 스트림과 연결 된 개체가 그렇지 않은 경우.  
  
 자세한 내용은 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namecreatememorystreama--colestreamfilecreatememorystream"></a><a name="creatememorystream"></a>COleStreamFile::CreateMemoryStream  
 안전 하 게 있는 경우 오류는 일반, 예상 된 조건이 전역 공유 메모리에서 새 스트림을 만듭니다.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pError`  
 가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 **NULL** 만들기 작업의 완료 상태를 나타내는입니다. 스트림을 만들 시도 하 여 생성 된 가능한 예외를 모니터링 하려는 경우이 매개 변수를 제공 합니다.  
  
### <a name="return-value"></a>반환 값  
 스트림이 성공적으로 만들어지면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메모리는 OLE 하위 시스템에 의해 할당 됩니다.  
  
 자세한 내용은 참조 [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namecreatestreama--colestreamfilecreatestream"></a><a name="createstream"></a>COleStreamFile::CreateStream  
 여기서 오류는 정상적이 고 예상 된 조건이 제공 되는 저장소 개체에 새 스트림을 안전 하 게 만듭니다.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpStorage`  
 만들려는 스트림을 포함 하는 OLE 저장소 개체를 가리킵니다. 안 **NULL**합니다.  
  
 `lpszStreamName`  
 만들 스트림의 이름입니다. 안 **NULL**합니다.  
  
 `nOpenFlags`  
 스트림을 열 때 사용할 액세스 모드입니다. 단독, 읽기/쓰기가 가능 하며 모드 만들 기본적으로 사용 됩니다. 사용 가능한 모드의 전체 목록은 참조 하십시오. [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)합니다.  
  
 `pError`  
 가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 **NULL**합니다. 스트림을 만들 시도 하 여 생성 된 가능한 예외를 모니터링 하려는 경우이 매개 변수를 제공 합니다.  
  
### <a name="return-value"></a>반환 값  
 스트림이 성공적으로 만들어지면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 열기 실패 하면 파일 예외가 throw 됩니다 및 `pError` 없는 **NULL**합니다.  
  
 자세한 내용은 참조 [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namedetacha--colestreamfiledetach"></a><a name="detach"></a>COleStreamFile::Detach  
 스트림을 닫지 않고 스트림을 개체에서 연결을 끊습니다.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>반환 값  
 스트림에 대 한 포인터 ( `IStream`) 된 개체와 연결 합니다.  
  
### <a name="remarks"></a>주의  
 프로그램을 종료 하기 전에 다른 방식으로 스트림을 닫아야 합니다.  
  
 자세한 내용은 참조 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetstreama--colestreamfilegetstream"></a><a name="getstream"></a>COleStreamFile::GetStream  
 현재 스트림에 대 한 포인터를 반환 하려면이 함수를 호출 합니다.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 스트림 인터페이스에 대 한 포인터 ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="a-nameopenstreama--colestreamfileopenstream"></a><a name="openstream"></a>COleStreamFile::OpenStream  
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
 스트림을 열 수를 포함 하는 OLE 저장소 개체를 가리킵니다. 안 **NULL**합니다.  
  
 `lpszStreamName`  
 열려는 스트림의 이름입니다. 안 **NULL**합니다.  
  
 `nOpenFlags`  
 스트림을 열 때 사용할 액세스 모드입니다. 전용 및 읽기/쓰기 모드는 기본적으로 사용 됩니다. 사용 가능한 모드의 전체 목록에 대 한 참조 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)합니다.  
  
 `pError`  
 가리키는 [CFileException](../../mfc/reference/cfileexception-class.md) 개체 또는 **NULL**합니다. 스트림을 열려고 시도 하 여 생성 된 가능한 예외를 모니터링 하려는 경우이 매개 변수를 제공 합니다.  
  
### <a name="return-value"></a>반환 값  
 스트림이 성공적으로 열린 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 열기 실패 하면 파일 예외가 throw 됩니다 및 `pError` 없는 **NULL**합니다.  
  
 자세한 내용은 참조 [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFile 클래스](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




