---
title: CSharedFile 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
dev_langs:
- C++
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bee22940fb197d480f4ae3550d8dd59780c256b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="csharedfile-class"></a>CSharedFile 클래스
[CMemFile](../../mfc/reference/cmemfile-class.md)-공유 메모리 파일을 지 원하는 클래스를 파생된 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|`CSharedFile` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|공유 메모리 파일을 닫고 해당 메모리 블록의 핸들을 반환 합니다.|  
|[CSharedFile::SetHandle](#sethandle)|공유 메모리 파일을 메모리 블록을 연결 합니다.|  
  
## <a name="remarks"></a>설명  
 파일이 디스크 대신 RAM에 저장 된 제외 하 고 메모리 파일 디스크 파일 처럼 동작 합니다. 메모리 파일 독립 프로세스 간에 개체를 직렬화 하거나 빠른 임시 저장소에 대 한 또는 원시 바이트를 전송 하는 데 유용 합니다.  
  
 공유 메모리 파일 달리 다른 메모리 파일에서 메모리에 할당 된는 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows 함수입니다. `CSharedFile` 전역적으로 할당 된 메모리 블록에 데이터를 저장 하는 클래스 (사용 하 여 만든 **GlobalAlloc**), DDE, 클립보드 또는 다른 OLE/COM 단일형 데이터 전송 작업의 경우 예를 들어,를 사용 하 여이 메모리 블록을 공유할 수 있습니다 사용 하 여 `IDataObject`합니다.  
  
 **GlobalAlloc** 반환는 `HGLOBAL` 처리에서 반환 된 포인터와 같은 메모리에 대 한 포인터 대신 [malloc](../../c-runtime-library/reference/malloc.md)합니다. `HGLOBAL` 핸들은 특정 응용 프로그램에 필요 합니다. 예를 들어 데이터에 두 클립보드 필요한는 `HGLOBAL` 처리 합니다.  
  
 유의 사항: `CSharedFile` 사용 메모리 매핑된 파일 하지 않으며 데이터 직접 프로세스 간에 공유할 수 없습니다.  
  
 `CSharedFile` 개체의 경우 자동으로 자체 메모리를 할당할 수 하거나 사용자 고유의 메모리 블록을 연결할 수 있습니다는 `CSharedFile` 호출 하 여 개체 [CSharedFile::SetHandle](#sethandle)합니다. 두 경우 모두 자동으로 증가 하 고 메모리 파일에 대 한 메모리에 할당 됩니다 `nGrowBytes`-크기 만큼 경우 `nGrowBytes` 0이 아닙니다.  
  
 자세한 내용은 문서 참조 [MFC의 파일](../../mfc/files-in-mfc.md) 및 [파일 처리](../../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxadv.h  
  
##  <a name="csharedfile"></a>  CSharedFile::CSharedFile  
 생성 된 `CSharedFile` 개체와 메모리를 할당 합니다.  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>매개 변수  
 *nAllocFlags*  
 메모리 할당 방법을 나타내는 플래그입니다. 참조 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) 올바른 플래그 값의 목록에 대 한 합니다.  
  
 `nGrowBytes`  
 바이트의 메모리 할당 증가 합니다.  
  
##  <a name="detach"></a>  CSharedFile::Detach  
 메모리 파일을 메모리 블록에서 컬렉션을 분리 하 여이 함수를 호출 합니다.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>반환 값  
 메모리 파일의 내용을 포함 하는 메모리 블록의 핸들입니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여 다시 열 수 있습니다 [SetHandle](#sethandle)에서 반환 된 핸들을 사용 하 여 **분리**합니다.  
  
##  <a name="sethandle"></a>  CSharedFile::SetHandle  
 전역 메모리 블록을 연결 하려면이 함수 호출의 `CSharedFile` 개체입니다.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *hGlobalMemory*  
 에 연결 될 글로벌 메모리에 대 한 핸들은 `CSharedFile`합니다.  
  
 `bAllowGrow`  
 메모리 블록 증가할 수 있는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 경우 `bAllowGrow` 0이 아닌 메모리 블록의 크기 증가 필요할 경우, 예를 들어 시도가 있으면 하려고 파일에서 메모리 블록에 할당 된 것 보다 더 많은 바이트를 쓰려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CMemFile 클래스](../../mfc/reference/cmemfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMemFile 클래스](../../mfc/reference/cmemfile-class.md)
