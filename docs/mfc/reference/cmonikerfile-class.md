---
title: "CMonikerFile 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile class
- monikers, MFC
- IMoniker interface, binding
- IMoniker interface
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
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
ms.openlocfilehash: 4668672af1b33170ece1cb4d449ed5a20f6040e7
ms.lasthandoff: 02/24/2017

---
# <a name="cmonikerfile-class"></a>CMonikerFile 클래스
데이터의 스트림을 나타냅니다 ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034))로 명명 된 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|`CMonikerFile` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|분리 및 스트림을 해제 하 고 모니커를 해제 합니다.|  
|[CMonikerFile::Detach](#detach)|분리 된 `IMoniker` 이 `CMonikerFile` 개체입니다.|  
|[CMonikerFile::GetMoniker](#getmoniker)|현재 모니커를 반환합니다.|  
|[CMonikerFile::Open](#open)|스트림을 가져올 수 지정된 된 파일을 엽니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|바인딩 컨텍스트를 얻거나 초기화 하는 기본 바인딩 컨텍스트를 만듭니다.|  
  
## <a name="remarks"></a>주의  
 모니커를 사용 하면 파일에 대 한 경로 이름 비슷하게 정보가 있습니다. 모니커 개체의에 대 한 포인터 있으면 `IMoniker` 인터페이스에는 파일은 실제로 위치 하는 방법에 대 한 기타 관련 정보를 필요 없이 식별된 된 파일에 대 한 액세스를 가져올 수 있습니다.  
  
 파생 된 `COleStreamFile`, `CMonikerFile` 모니커 또는 모니커를 가능 하 게 문자열 표현을 사용 하 고 있는 모니커가 이름을 스트림에 바인딩합니다. 그런 다음 읽기 하 고 해당 스트림에 쓸 수 있습니다. 실제 목적 `CMonikerFile` 에 대 한 간단한 액세스를 제공 하는 `IStream`s로 명명 `IMoniker`s에 스트림을 직접 바인딩할 필요가 없도록 아직 `CFile` 스트림에 기능입니다.  
  
 `CMonikerFile`스트림을 이외의 값으로 바인딩할 사용할 수 없습니다. 저장소 또는 개체에 바인딩할 경우 사용 해야는 `IMoniker` 인터페이스를 직접.  
  
 모니커 및 스트림에 대 한 자세한 내용은 참조 하십시오. [COleStreamFile](../../mfc/reference/colestreamfile-class.md) 에 *MFC 참조* 및 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 및 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="close"></a>CMonikerFile::Close  
 분리 및 스트림을 해제 하 고 모니커를 해제 하려면이 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>주의  
 열려 있지 않은 또는 이미 닫힌 스트림에서 호출할 수 있습니다.  
  
##  <a name="cmonikerfile"></a>CMonikerFile::CMonikerFile  
 `CMonikerFile` 개체를 생성합니다.  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>CMonikerFile::CreateBindContext  
 초기화 하는 기본 바인딩 컨텍스트를 만들려면이 함수를 호출 합니다.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>매개 변수  
 `pError`  
 파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 바인딩 컨텍스트에 대 한 포인터 [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) 성공 하 고 그렇지 않으면 사용 하 여 바인딩할 **NULL**합니다. 인스턴스가으로 열렸으면 하는 경우는 `IBindHost` 인터페이스를 바인딩 컨텍스트에에서 검색 되는 `IBindHost`합니다. 없을 경우 없는 `IBindHost` 인터페이스 또는 인터페이스를 바인딩 컨텍스트를 반환 하지 못하는, 바인딩 컨텍스트가 생성 됩니다. 에 대 한 설명은 [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 바인딩 컨텍스트는 특정 모니커 바인딩 작업에 대 한 정보를 저장 하는 개체입니다. 사용자 지정 바인딩 컨텍스트를 제공 하려면이 함수를 재정의할 수 있습니다.  
  
##  <a name="detach"></a>CMonikerFile::Detach  
 이 함수는 스트림의 닫을를 호출 합니다.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pError`  
 파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="getmoniker"></a>CMonikerFile::GetMoniker  
 현재 모니커에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 모니커 인터페이스에 대 한 포인터 ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>주의  
 이후 `CMonikerFile` 는 인터페이스에 없는 반환 된 포인터의 참조 횟수를 증가 하지 않습니다 (통해 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), 모니커를 눌렀다 때는 `CMonikerFile` 개체가 해제 되는 합니다. 모니커를 점유 하거나 직접 해제 하려는 경우, `AddRef` 것입니다.  
  
##  <a name="open"></a>CMonikerFile::Open  
 파일 또는 모니커 개체를이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszURL`  
 URL 또는 파일을 열 수의 파일 이름입니다.  
  
 `pError`  
 파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.  
  
 `pMoniker`  
 모니커 인터페이스에 대 한 포인터 `IMoniker` 는 데 사용할 스트림을 가져올 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 `lpszURL` Macintosh에서 매개 변수를 사용할 수 없습니다. 만 `pMoniker` 형태의 **열려** Macintosh에서 사용할 수 있습니다.  
  
 URL 또는 파일 이름을 사용할 수는 `lpszURL` 매개 변수입니다. 예:  
  
 [!code-cpp[NVC_MFCWinInet #&6;](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 -또는-  
  
 [!code-cpp[NVC_MFCWinInet #&7;](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [COleStreamFile 클래스](../../mfc/reference/colestreamfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile 클래스](../../mfc/reference/casyncmonikerfile-class.md)

