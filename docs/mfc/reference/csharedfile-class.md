---
title: "CSharedFile 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- memory files
- CSharedFile class
- shared memory files
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: 21
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f812b2c7b8e3b158068bf3fdab0a327460056251
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
|[CSharedFile::Detach](#detach)|공유 메모리 파일을 닫고 메모리 블록의 핸들을 반환 합니다.|  
|[CSharedFile::SetHandle](#sethandle)|공유 메모리 파일을 메모리 블록을 연결 합니다.|  
  
## <a name="remarks"></a>주의  
 메모리 내 파일 파일은 RAM에 아닌 디스크에 저장 한다는 점을 제외 하면 디스크 파일 처럼 작동 합니다. 메모리 파일 빠른 임시 저장소에 대 한 원시 바이트를 전송 하는 데 유용 하거나 독립 프로세스 간에 개체를 직렬화 합니다.  
  
 메모리에 할당 된 공유 메모리 파일 다른 메모리 파일에서 차이점이 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows 함수입니다. `CSharedFile` 전역적으로 할당 된 메모리 블록에 데이터를 저장 하는 클래스 (사용 하 여 만든 **GlobalAlloc**), 메모리 블록 공유할 수 있는 DDE, 클립보드 또는 다른 OLE/COM 단일형 데이터 전송 작업의 경우 예를 들어를 사용 하 여 사용 하 여 `IDataObject`합니다.  
  
 **GlobalAlloc** 반환는 `HGLOBAL` 의해 반환 된 포인터와 같은 메모리에 대 한 포인터는 대신 처리 [malloc](../../c-runtime-library/reference/malloc.md)합니다. `HGLOBAL` 핸들 특정 응용 프로그램에 필요 합니다. 예를 들어 데이터에 두 클립보드 필요한는 `HGLOBAL` 처리 합니다.  
  
 유의 사항: `CSharedFile` 사용 하 여 메모리 매핑된 파일의 역할과 프로세스 간에 데이터를 직접 공유할 수 없습니다.  
  
 `CSharedFile`개체의 경우 자동으로 자신의 메모리를 할당할 수 또는 고유한 메모리 블록을 연결할 수는 `CSharedFile` 개체를 호출 하 여 [CSharedFile::SetHandle](#sethandle)합니다. 두 경우 모두 메모리 파일의 크기를 자동으로 증가 하는 것에 대 한 메모리에서 할당 되는 `nGrowBytes`-경우 크기 만큼 `nGrowBytes`&0;이 아닙니다.  
  
 자세한 내용은 문서를 참조 하십시오. [MFC의 파일](../../mfc/files-in-mfc.md) 및 [파일 처리](../../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxadv.h  
  
##  <a name="csharedfile"></a>CSharedFile::CSharedFile  
 생성 된 `CSharedFile` 개체 및 메모리를 할당 합니다.  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>매개 변수  
 *nAllocFlags*  
 메모리 할당 하는 하는 방법을 나타내는 플래그입니다. 참조 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) 목록은 유효한 플래그 값입니다.  
  
 `nGrowBytes`  
 바이트의 메모리 할당 증가 합니다.  
  
##  <a name="detach"></a>CSharedFile::Detach  
 메모리 파일을 메모리 블록에서 분리 하 여이 함수를 호출 합니다.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>반환 값  
 메모리 파일의 내용을 포함 하는 메모리 블록의 핸들입니다.  
  
### <a name="remarks"></a>주의  
 호출 하 여 다시 열 수 있습니다 [SetHandle](#sethandle)에서 반환 된 핸들을 사용 하 여 **분리**합니다.  
  
##  <a name="sethandle"></a>CSharedFile::SetHandle  
 글로벌 메모리 블록을 연결 하려면이 함수를 호출 하 여 `CSharedFile` 개체입니다.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *hGlobalMemory*  
 에 연결 되는 전역 메모리에 대 한 핸들의 `CSharedFile`합니다.  
  
 `bAllowGrow`  
 메모리 블록이 증가 하도록 허용 되는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 경우 `bAllowGrow` 메모리 블록의 크기 증가 필요할 경우, 예를 들어 시도가 있으면&0;이 아닌 이루어집니다 파일에서 메모리 블록에 할당 된 것 보다 더 많은 바이트를 쓰려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CMemFile 클래스](../../mfc/reference/cmemfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMemFile 클래스](../../mfc/reference/cmemfile-class.md)

