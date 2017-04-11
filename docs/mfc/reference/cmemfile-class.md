---
title: "CMemFile 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
dev_langs:
- C++
helpviewer_keywords:
- memory files
- CMemFile class
- temporary files, memory files
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
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
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 735f0a5653782f6f42b9dc9ad20e91e94a825f6c
ms.lasthandoff: 04/04/2017

---
# <a name="cmemfile-class"></a>CMemFile 클래스
[CFile](../../mfc/reference/cfile-class.md)-을 지 원하는 메모리 파일 클래스를 파생 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|메모리 파일 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|메모리 블록을 연결 `CMemFile`합니다.|  
|[CMemFile::Detach](#detach)|메모리 블록을 분리 `CMemFile` 분리 하는 메모리 블록에 대 한 포인터를 반환 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|메모리 할당 동작을 수정 하려면 재정의 합니다.|  
|[CMemFile::Free](#free)|메모리 할당 취소 동작을 수정 하려면 재정의 합니다.|  
|[CMemFile::GrowFile](#growfile)|파일 증가 때 동작을 수정 하려면 재정의 합니다.|  
|[CMemFile::Memcpy](#memcpy)|파일 읽기 및 쓰기 때 메모리 복사 동작을 수정 하려면 재정의 합니다.|  
|[CMemFile::Realloc](#realloc)|메모리 재할당 동작을 수정 하려면 재정의 합니다.|  
  
## <a name="remarks"></a>주의  
 이러한 메모리 내 파일 제외 하 고 파일이 디스크 대신 RAM에 저장 된 디스크 파일 처럼 동작 합니다. 메모리 파일 독립 프로세스 간에 개체를 직렬화 하거나 빠른 임시 저장소에 대 한 또는 원시 바이트를 전송 하는 데 유용 합니다.  
  
 `CMemFile`개체의 경우 자동으로 자체 메모리를 할당할 수 하거나 사용자 고유의 메모리 블록을 연결할 수 있습니다는 `CMemFile` 호출 하 여 개체 [연결](#attach)합니다. 두 경우 모두 자동으로 증가 하 고 메모리 파일에 대 한 메모리에 할당 됩니다 `nGrowBytes`-크기 만큼 경우 `nGrowBytes` 0이 아닙니다.  
  
 메모리 블록의 소멸 시 자동으로 삭제 됩니다는 `CMemFile` 메모리에서 원래 할당 된 개체는 `CMemFile` 개체, 개체에 연결 하는 메모리 할당 해제를 담당 하 고, 그러지 않으면 합니다.  
  
 메모리 블록에서 분리 하는 경우 제공 된 포인터를 통해 액세스할 수 있습니다는 `CMemFile` 호출 하 여 개체 [분리](#detach)합니다.  
  
 가장 일반적인 용도 `CMemFile` 만드는 것을 `CMemFile` 개체를 호출 하 여 사용할 [CFile](../../mfc/reference/cfile-class.md) 멤버 함수입니다. 만드는 참고는 `CMemFile` 자동으로 열립니다: 호출 하지 않으면 [CFile::Open](../../mfc/reference/cfile-class.md#open), 디스크 파일에만 사용 됩니다. 때문에 `CMemFile` 디스크 파일의 경우 데이터 멤버를 사용 하지 않는 `CFile::m_hFile` 사용 되지 않습니다.  
  
 `CFile` 멤버 함수 [중복](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), 및 [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) 에 대 한 구현 되지 않은 `CMemFile`합니다. 이러한 함수를 호출 하는 경우는 `CMemFile` 개체를 얻게 됩니다는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.  
  
 `CMemFile`런타임 라이브러리 함수를 사용 하 여 [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md), 및 [무료](../../c-runtime-library/reference/free.md) 를 할당 하려면 다시 할당 및 메모리; 및 내장 할당 취소 [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) 읽고 쓸 때 블록 복사본 메모리에 있습니다. 이 동작 또는 동작을 변경 하 시겠습니까 때 `CMemFile` 증가 하는 파일에서 고유한 클래스를 파생 `CMemFile` 고 적절 한 함수를 무시 합니다.  
  
 대 한 자세한 내용은 `CMemFile`, 문서를 참조 [MFC의 파일](../../mfc/files-in-mfc.md) 및 [메모리 관리 (MFC)](../../mfc/memory-management.md) 참조 및 [파일 처리](../../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="alloc"></a>CMemFile::Alloc  
 이 함수를 호출 하 `CMemFile` 멤버 함수입니다.  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 에 할당할 메모리의 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 할당 된 메모리 블록에 대 한 포인터 또는 **NULL** 할당에 실패 한 경우.  
  
### <a name="remarks"></a>주의  
 사용자 지정 메모리 할당을 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우 해도 좋을 것을 재정의 하 [무료](#free) 및 [Realloc](#realloc) 도 합니다.  
  
 런타임 라이브러리 함수를 사용 하는 기본 구현은 [malloc](../../c-runtime-library/reference/malloc.md) 메모리를 할당 합니다.  
  
##  <a name="attach"></a>CMemFile::Attach  
 메모리 블록을 연결 하려면이 함수를 호출 `CMemFile`합니다.  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuffer`  
 에 연결 될 버퍼에 대 한 포인터 `CMemFile`합니다.  
  
 `nBufferSize`  
 버퍼의 크기를 바이트 단위로 지정 하는 정수입니다.  
  
 `nGrowBytes`  
 바이트의 메모리 할당 증가 합니다.  
  
### <a name="remarks"></a>주의  
 이 인해 `CMemFile` 메모리 파일로 메모리 블록을 사용 하도록 합니다.  
  
 경우 `nGrowBytes` 은 0으로, `CMemFile` 파일 길이를 설정 하는 `nBufferSize`합니다. 즉, 메모리 블록의 데이터에 연결 되었던 전에 `CMemFile` 파일로 사용 됩니다. 이러한 방법으로 만든 메모리 파일을 확장 시킬 수 없습니다.  
  
 파일 증가 수 없으므로, 발생 하지 않도록 주의 해야 `CMemFile` 파일 증가 하려고 합니다. 예를 들어 호출 하지 마세요는 `CMemFile` 의 재정의 [CFile:Write](../../mfc/reference/cfile-class.md#write) 에 끝을 지나서 쓰거나 호출 하지 마세요 [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) 보다 긴 길이가 `nBufferSize`합니다.  
  
 경우 `nGrowBytes` 0 보다 크면 `CMemFile` 부착 된 메모리 블록의 내용을 무시 합니다. 메모리 파일의 내용을 사용 하 여 처음부터 작성 해야 합니다.는 `CMemFile` 의 재정의 `CFile::Write`합니다. 호출 하 여 증가 된 파일 또는 파일의 끝을 지나서 쓰기 시도 `CMemFile` 의 재정의 `CFile::SetLength`, `CMemFile` 씩에서 메모리 할당 크기가 계속 커집니다 `nGrowBytes`합니다. 메모리 블록에 전달 하는 경우 증가 하는 메모리 할당에 실패 합니다 **연결** 와 호환 되는 메서드를 사용 하 여 할당 되지 않은 [Alloc](#alloc)합니다. 기본 구현은와 호환 되도록 `Alloc`, 런타임 라이브러리 함수가 메모리를 할당 해야 [malloc](../../c-runtime-library/reference/malloc.md) 또는 [calloc](../../c-runtime-library/reference/calloc.md)합니다.  
  
##  <a name="cmemfile"></a>CMemFile::CMemFile  
 첫 번째 오버 로드는 빈 메모리 파일을 엽니다.  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nGrowBytes`  
 바이트의 메모리 할당 증가 합니다.  
  
 *lpBuffe*r  
 크기의 정보를 수신 하는 버퍼에 대 한 포인터 `nBufferSize`합니다.  
  
 `nBufferSize`  
 파일 버퍼의 크기를 바이트 단위로 지정 하는 정수입니다.  
  
### <a name="remarks"></a>설명  
 생성자가 파일을 열 표시 되 고 호출 하지 않아야 [CFile::Open](../../mfc/reference/cfile-class.md#open)합니다.  
  
 첫 번째 생성자를 사용 하 고 즉시 호출 하는 경우에 따라 동일 하 게 두 번째 오버 로드 동작 [연결](#attach) 동일한 매개 변수를 사용 합니다. 참조 **연결** 대 한 자세한 내용은 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles # 36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>CMemFile::Detach  
 사용 하 고 메모리 블록에 대 한 포인터를 가져오려면이 함수를 호출 `CMemFile`합니다.  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>반환 값  
 메모리 파일의 내용을 포함 하는 메모리 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 닫습니다. 또한 호출는 `CMemFile`합니다. 메모리 블록 다시 연결할 수 있습니다 `CMemFile` 호출 하 여 [연결](#attach)합니다. 호출 해야 파일을 다시 연결 하 고 그 안에 데이터를 사용 하려는 경우 [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) 호출 하기 전에 파일의 길이를 가져오는 **분리**합니다. 메모리 블록을 연결 하는 경우 유의 `CMemFile` 해당 데이터를 사용할 수 있도록 ( `nGrowBytes` = = 0), 메모리 파일을 확장할 수 없습니다.  
  
##  <a name="free"></a>CMemFile::Free  
 이 함수를 호출 하 `CMemFile` 멤버 함수입니다.  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpMem`  
 메모리 할당을 취소할 수에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 사용자 지정 메모리 할당 취소를 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우 해도 좋을 것을 재정의 하 [Alloc](#alloc) 및 [Realloc](#realloc) 도 합니다.  
  
##  <a name="growfile"></a>CMemFile::GrowFile  
 이 함수 중 일부에 의해 호출 됩니다는 `CMemFile` 멤버 함수입니다.  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwNewLen`  
 메모리 파일의 새 크기입니다.  
  
### <a name="remarks"></a>주의  
 변경 하려는 경우에 재정의할 수 있습니다 어떻게 `CMemFile` 해당 파일을 늘립니다. 기본 구현 호출 [Realloc](#realloc) 기존 블록을 증가 (또는 [Alloc](#alloc) 메모리 블록을 만듭니다)의 배수로 메모리를 할당 하는 `nGrowBytes` 생성자에 지정 된 값 또는 [연결](#attach) 호출 합니다.  
  
##  <a name="memcpy"></a>CMemFile::Memcpy  
 이 함수 호출 됩니다는 `CMemFile` 의 재정의 [CFile::Read](../../mfc/reference/cfile-class.md#read) 및 [CFile::Write](../../mfc/reference/cfile-class.md#write) 하 고 메모리 파일에서 데이터를 전송 합니다.  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpMemTarget`  
 소스 메모리를 복사할 메모리 블록에 대 한 포인터입니다.  
  
 `lpMemSource`  
 소스 메모리 블록에 대 한 포인터입니다.  
  
 `nBytes`  
 복사할 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 `lpMemTarget`의 복사본입니다.  
  
### <a name="remarks"></a>주의  
 방식을 변경 하려는 경우이 함수를 재정의 하는 `CMemFile` 이러한 메모리 복사본 않습니다.  
  
##  <a name="realloc"></a>CMemFile::Realloc  
 이 함수를 호출 하 `CMemFile` 멤버 함수입니다.  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpMem`  
 메모리 블록 다시 할당 될 수에 대 한 포인터입니다.  
  
 `nBytes`  
 메모리 블록에 대 한 새 크기입니다.  
  
### <a name="return-value"></a>반환 값  
 메모리 블록 다시 할당 (되었으며 이동 가능)에 대 한 포인터 또는 **NULL** 경우 재할당 실패 한 경우.  
  
### <a name="remarks"></a>주의  
 사용자 지정 메모리 재할당 구현 하려면이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우 해도 좋을 것을 재정의 하 [Alloc](#alloc) 및 [무료](#free) 도 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFile 클래스](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




