---
title: "CAtlFileMappingBase 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b5e0dd90894e052d4b9bcff08e7e12234dde8f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase 클래스
이 클래스는 메모리 매핑된 파일을 나타냅니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|생성자입니다.|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|파일 매핑 개체에서 복사 하려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::GetData](#getdata)|파일 매핑 개체에서 데이터를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|파일 핸들을 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|파일 매핑 개체에서 매핑 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::MapFile](#mapfile)|파일 매핑 개체를 만들려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|모든 프로세스에 대 한 모든 권한을 허용 된 파일 매핑 개체를 만들려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|파일 매핑 개체에 대 한 핸들을 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::Unmap](#unmap)|파일 매핑 개체의 매핑을 해제 하려면이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|다른 파일 매핑 개체를 현재 파일 매핑 개체를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 파일 매핑 프로세스의 가상 주소 공간 부분과 파일 내용의 연결입니다. 이 클래스는 프로그램을 쉽게 액세스 하 고 데이터 공유를 허용 하는 파일 매핑 개체를 만들기 위한 메서드를 제공 합니다.  
  
 자세한 내용은 참조 [파일 매핑](http://msdn.microsoft.com/library/windows/desktop/aa366556) Windows sdk에서입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlfile.h  
  
##  <a name="catlfilemappingbase"></a>CAtlFileMappingBase::CAtlFileMappingBase  
 생성자입니다.  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `orig`  
 새 개체를 만드는 복사할 원본 파일 매핑 개체를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 필요에 따라 기존 개체를 사용 하 여 새 파일 매핑 개체를 만듭니다. 호출 해야 [CAtlFileMappingBase::MapFile](#mapfile) 특정 파일에 대 한 파일 매핑 개체를 만들거나 열 수 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 소멸자입니다.  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>설명  
 클래스 및 호출 하 여 할당 된 리소스를 해제는 [CAtlFileMappingBase::Unmap](#unmap) 메서드.  
  
##  <a name="copyfrom"></a>CAtlFileMappingBase::CopyFrom  
 파일 매핑 개체에서 복사 하려면이 메서드를 호출 합니다.  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `orig`  
 복사할 원본 파일 매핑 개체를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
##  <a name="getdata"></a>CAtlFileMappingBase::GetData  
 파일 매핑 개체에서 데이터를 가져오려면이 메서드를 호출 합니다.  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 데이터에 대 한 포인터를 반환합니다.  
  
##  <a name="gethandle"></a>CAtlFileMappingBase::GetHandle  
 파일 매핑 개체에 대 한 핸들을 반환 하려면이 메서드를 호출 합니다.  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>반환 값  
 파일 매핑 개체에 대 한 핸들을 반환합니다.  
  
##  <a name="getmappingsize"></a>CAtlFileMappingBase::GetMappingSize  
 파일 매핑 개체에서 매핑 크기를 가져오려면이 메서드를 호출 합니다.  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>반환 값  
 매핑 크기를 반환합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)합니다.  
  
##  <a name="mapfile"></a>CAtlFileMappingBase::MapFile  
 지정된 된 파일에 대 한 파일 매핑 개체를 만들거나 열 수 있는이 메서드를 호출 합니다.  
  
```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hFile`  
 매핑 개체를 만드는 데 사용할 파일에 대 한 핸들입니다. `hFile`유효 해야 하며 INVALID_HANDLE_VALUE로 설정할 수 없습니다.  
  
 `nMappingSize`  
 매핑 크기입니다. 파일 매핑 개체의 최대 크기는로 식별 되는 파일의 현재 크기와 같은 0 인 경우, *hFile 합니다.*  
  
 `nOffset`  
 매핑이 시작 될 파일 오프셋입니다. 오프셋된 값은 시스템의 메모리 할당 세분성의 배수 여야 합니다.  
  
 `dwMappingProtection`  
 파일을 매핑할 때 필요한 파일 보기에 대 한 보호 합니다. 참조 `flProtect` 에 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) in the Windows SDK입니다.  
  
 `dwViewDesiredAccess`  
 파일 보기 및 이므로 파일에서 매핑된 페이지 보호에 대 한 액세스 유형을 지정 합니다. 참조 `dwDesiredAccess` 에 [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) in the Windows SDK입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 파일 매핑 개체를 만든 후 파일의 크기 초과할 수 없습니다; 파일 매핑 개체의 크기 그렇지 않으면 모든 파일의 내용을 공유 하는 데 사용할 수 있는 됩니다. 자세한 내용은 참조 하십시오. [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) 및 [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 예를 참조 [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)합니다.  
  
##  <a name="mapsharedmem"></a>CAtlFileMappingBase::MapSharedMem  
 모든 프로세스에 대 한 모든 권한을 허용 된 파일 매핑 개체를 만들려면이 메서드를 호출 합니다.  
  
```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nMappingSize`  
 매핑 크기입니다. 파일 매핑 개체의 최대 크기는 식별 되는 파일 매핑 개체의 현재 크기와 같은 0 인 경우,`szName.`  
  
 `szName`  
 매핑 개체의 이름입니다.  
  
 *pbAlreadyExisted*  
 가리키는 BOOL 값으로 설정 된 경우 TRUE 매핑 개체 이미 존재 합니다.  
  
 `lpsa`  
 에 대 한 포인터는 **SECURITY_ATTRIBUTES** 자식 프로세스에 의해 반환된 된 핸들을 상속할 수 있는지 여부를 결정 하는 구조체. 참조 *lpAttributes* 에 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) Windows sdk에서입니다.  
  
 `dwMappingProtection`  
 파일을 매핑할 때 필요한 파일 보기에 대 한 보호 합니다. 참조 `flProtect` 에 **CreateFileMapping** in the Windows SDK입니다.  
  
 `dwViewDesiredAccess`  
 파일 보기 및 이므로 파일에서 매핑된 페이지 보호에 대 한 액세스 유형을 지정 합니다. 참조 `dwDesiredAccess` 에 [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) in the Windows SDK입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 **MapShareMem** 에서 만든 기존 파일 매핑 개체를 사용 하면 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537), 프로세스 간에 공유할 수 있습니다.  
  
##  <a name="openmapping"></a>CAtlFileMappingBase::OpenMapping  
 지정된 된 파일에 대 한 명명 된 파일 매핑 개체를이 메서드를 호출 합니다.  
  
```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `szName`  
 매핑 개체의 이름입니다. 이 이름으로 파일 매핑 개체에 대해 열린 핸들이 있고 매핑 개체에서 보안 설명자와 충돌 하지 않는 경우는 `dwViewDesiredAccess` 매개 변수를 열기 작업이 성공 합니다.  
  
 `nMappingSize`  
 매핑 크기입니다. 파일 매핑 개체의 최대 크기는 식별 되는 파일 매핑 개체의 현재 크기와 같은 0 인 경우,`szName.`  
  
 `nOffset`  
 매핑이 시작 될 파일 오프셋입니다. 오프셋된 값은 시스템의 메모리 할당 세분성의 배수 여야 합니다.  
  
 `dwViewDesiredAccess`  
 파일 보기 및 이므로 파일에서 매핑된 페이지 보호에 대 한 액세스 유형을 지정 합니다. 참조 `dwDesiredAccess` 에 [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) in the Windows SDK입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류는 입력된 매개 변수가 유효 하지 않은 경우 발생 합니다.  
  
##  <a name="operator_eq"></a>CAtlFileMappingBase::operator =  
 다른 파일 매핑 개체를 현재 파일 매핑 개체를 설정합니다.  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>매개 변수  
 `orig`  
 현재 파일 매핑 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 개체에 대 한 참조를 반환합니다.  
  
##  <a name="unmap"></a>CAtlFileMappingBase::Unmap  
 파일 매핑 개체의 매핑을 해제 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 참조 [UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882) 자세한 내용을 보려면 Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlFileMapping 클래스](../../atl/reference/catlfilemapping-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
