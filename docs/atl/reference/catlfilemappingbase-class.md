---
title: "CAtlFileMappingBase 클래스 | Microsoft 문서"
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 439f123bc0addbbec2a26102d0197d0a1f14a8d5
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
|[CAtlFileMappingBase::MapFile](#mapfile)|파일 매핑 개체를 생성 하도록이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|모든 프로세스에 대 한 전체 액세스를 허용 하는 파일 매핑 개체를 생성 하도록이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|파일 매핑 개체에 대 한 핸들을 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::Unmap](#unmap)|파일 매핑 개체의 매핑을 해제 하려면이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|다른 파일 매핑 개체를 현재 파일 매핑 개체를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 파일 매핑 프로세스의 가상 주소 공간 부분과 파일 내용 연결 하는 것입니다. 이 클래스는 쉽게 액세스 하 여 데이터를 공유 하는 프로그램을 허용 하는 파일 매핑 개체를 만들기 위한 메서드를 제공 합니다.  
  
 자세한 내용은 참조 [파일 매핑](http://msdn.microsoft.com/library/windows/desktop/aa366556) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
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
 새 개체를 복사할 원본 파일 매핑 개체입니다.  
  
### <a name="remarks"></a>주의  
 선택적으로 기존 개체를 사용 하 여 새 파일 매핑 개체를 만듭니다. 도 호출 해야 하는 [CAtlFileMappingBase::MapFile](#mapfile) 를 열거나 특정 파일에 대 한 파일 매핑 개체를 만듭니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&71;](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 소멸자입니다.  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>주의  
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
  
### <a name="example"></a>예제  
 예를 참조 [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)합니다.  
  
##  <a name="mapfile"></a>CAtlFileMappingBase::MapFile  
 지정된 된 파일에 대 한 파일 매핑 개체를 만들거나 열에이 메서드를 호출 합니다.  
  
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
 매핑 시작 되는 파일 오프셋입니다. 오프셋된 값은 시스템의 메모리 할당 세분성의 배수 여야 합니다.  
  
 `dwMappingProtection`  
 파일에 매핑되면 파일 보기에 대 한 원하는 보호 합니다. 참조 `flProtect` 에서 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwViewDesiredAccess`  
 파일 보기 및 이므로 파일에서 매핑된 페이지 보호에 대 한 액세스 유형을 지정 합니다. 참조 `dwDesiredAccess` 에서 [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>주의  
 파일 매핑 개체;의 크기를 파일의 크기에 넘지 않아야 파일 매핑 개체를 만든 후 그렇지 않으면 파일의 내용 중 일부만 공유용 제공 됩니다. 자세한 내용은 다음을 참조 하십시오. [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) 및 [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)합니다.  
  
##  <a name="mapsharedmem"></a>CAtlFileMappingBase::MapSharedMem  
 모든 프로세스에 대 한 전체 액세스를 허용 하는 파일 매핑 개체를 생성 하도록이 메서드를 호출 합니다.  
  
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
 가리키는 BOOL 값으로 설정 된 경우 TRUE를 매핑 개체 이미 존재 합니다.  
  
 `lpsa`  
 에 대 한 포인터는 **SECURITY_ATTRIBUTES** 자식 프로세스에 의해 반환 된 핸들을 상속할 수 있는지 여부를 결정 하는 구조체입니다. 참조 *lpAttributes* 에서 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwMappingProtection`  
 파일에 매핑되면 파일 보기에 대 한 원하는 보호 합니다. 참조 `flProtect` 에서 **CreateFileMapping** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwViewDesiredAccess`  
 파일 보기 및 이므로 파일에서 매핑된 페이지 보호에 대 한 액세스 유형을 지정 합니다. 참조 `dwDesiredAccess` 에서 [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>주의  
 **MapShareMem** 에서 만든 기존 파일 매핑 개체를 사용 하면 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537)를 프로세스 간에 공유할 수 있습니다.  
  
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
 매핑 개체의 이름입니다. 이 이름으로 파일 매핑 개체에 대해 열린 핸들이 고 매핑 개체에서 보안 설명자와 충돌 하지는 `dwViewDesiredAccess` 매개 변수를 열기 작업이 성공 합니다.  
  
 `nMappingSize`  
 매핑 크기입니다. 파일 매핑 개체의 최대 크기는 식별 되는 파일 매핑 개체의 현재 크기와 같은 0 인 경우,`szName.`  
  
 `nOffset`  
 매핑 시작 되는 파일 오프셋입니다. 오프셋된 값은 시스템의 메모리 할당 세분성의 배수 여야 합니다.  
  
 `dwViewDesiredAccess`  
 파일 보기 및 이므로 파일에서 매핑된 페이지 보호에 대 한 액세스 유형을 지정 합니다. 참조 `dwDesiredAccess` 에서 [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>주의  
 디버그 빌드에서 입력된 매개 변수가 유효 하지 않으면 어설션 오류가 발생 합니다.  
  
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
  
### <a name="remarks"></a>주의  
 참조 [UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlFileMapping 클래스](../../atl/reference/catlfilemapping-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

